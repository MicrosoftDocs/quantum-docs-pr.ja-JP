---
title: 'Q # 標準ライブラリ-エラー修正 |Microsoft Docs'
description: 'Q # 標準ライブラリ-エラー修正'
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5aac40686ba9b45a51e0274a1828f2ff7cce6fc3
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184442"
---
# <a name="error-correction"></a>エラーの修正 #

## <a name="introduction"></a>はじめる ##

従来のコンピューティングでは、エラーに対して1つの保護が必要な場合は、データビットを繰り返すことによって、そのビットを*論理ビット*で表現するのが十分な場合があります。
たとえば、$ >{0} = $0 はデータビット0のエンコーディングになります。この場合、ラベル0の上の行を使用して、0状態のビットのエンコーディングであることを示します。
同様に $-{1} = $111 を使用すると、1つのビットフリップエラーから保護する単純な繰り返しコードが作成されます。
つまり、3つのビットのいずれかが反転されている場合は、過半数の投票を行って論理ビットの状態を復旧できます。
古典的なエラー修正は、この特定の例 ([コード理論の概要を説明する](https://www.springer.com/us/book/9783540641339)ことをお勧めします) の方がはるかに豊富ですが、上記の繰り返しコードでは、クォンタム情報の保護に関する問題が既に考えられています。
つまり、[複製なしの定理](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem)は、個々の qubit を測定して、上記の古典的なコードと比較して大部分の投票を行うと、保護しようとしている正確な情報が失われていることを意味します。

[クォンタム] 設定には、測定値が問題であることが表示されます。 上記のエンコードを実装することもできます。
これを行うと、エラー修正をクォンタムケースに一般化する方法を確認することができます。
このため、let $ \ket{\overline{0}} = \ket{000} = \ket{0}/otimes \ket{0}/otimes \ket{0}$、let $ \ket{\overline{1}} = \ket{111}$。
次に、直線性により、すべての入力に対して繰り返しコードを定義しました。たとえば、$ \ket{\overline{+}} = (\ket{\overline{0}} + \ket{\overline{1}})/\ sqrt{2} = (\ket{000} + \ket{111})//sqrt{2}$ のようになります。
特に、ビットフリップエラーによって真ん中の qubit に _1 $ act $X すると、両方の分岐で必要とされる修正が $X _1 $: $ $ \begin{align} X_1 \ket{\overline{+}} & ={1}{/sqrt{2}}/left (X_1 \ket{000} + X_1 \ket{111} \ right) \\\\ & = \ frac{1}{\ sqrt{2}} \ 左 (\ket{010} + \ket{101} 右) です。
\end{align} $ $

保護しようとしている状態を測定せずにこの問題が発生していることを特定する方法を確認するには、それぞれのビットフリップエラーが論理的な状態にどのようになるかを記述することをお勧めします。

| エラー $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ |
| --- | --- | --- |
| $ \ bold 完了 $ | $ \ket{000}$ | $ \ket{111}$ |
| $X 0 $ (_d) | $ \ket{100}$ | $ \ket{011}$ |
| $X _1 $ | $ \ket{010}$ | $ \ket{101}$ |
| $X _2 $ | $ \ket{001}$ | $ \ket{110}$ |

エンコードされている状態を保護するためには、3つのエラーを相互に区別できる必要があります。また、$ \ket{\overline{0}} $ と $ \ket{\overline{1}} $ を区別せずに、id $ > から id $ > を区別できるようにする必要があります。
たとえば、$Z 0 $ を測定する場合、$ \ket{\overline{0}} $ および $ \ket{\overline{1}} $ に対して、エラーなしのケースでは異なる結果が得られるため、はエンコードされた状態を折りたたみます。
一方、各計算基準の状態の最初の2ビットのパリティである $Z 0 Z_1 $ を測定することを検討してください。
Pauli 演算子の各測定値がどの eigenvalue に対応しているかを確認します。そのため、上の表の各州 $ \ket{\psi} $ では、0 Z_1 \ket{\psi} $ を $Z 計算して $ \pm\ket{\psi} $ を取得できるかどうかを確認できます。
$Z 0 Z_1 \ket{000} = \ket{000}$ と $Z 0 Z_1 \ket{111} = \ket{111}$ であることに注意してください。そのため、この測定では、エンコードされた両方の状態が同じであることが結論となります。
一方、$Z 0 Z_1 \ket{100} =-\ket{100}$ and $Z 0 Z_1 \ket{011} =-\ket{011}$ を指定すると、0 Z_1 $ の測定結果によって、発生したエラーに関する有用な情報が示されます。

これを強調するために、上記の表を繰り返しますが、各行に 0 Z_1 $ と $Z _1 Z_2 $ $Z 測定した結果を追加します。
各測定の結果は、それぞれ、`Zero` と `One`の Q # `Result` 値に対応する、$ + $ または $-$ のいずれかの eigenvalue の符号によって示されます。

| エラー $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ | $Z 0 Z_1 $ の結果 (_s) | $Z _1 Z_2 $ の結果 |
| --- | --- | --- | --- | --- |
| $ \ bold 完了 $ | $ \ket{000}$ | $ \ket{111}$ | $+$ | $+$ |
| $X 0 $ (_d) | $ \ket{100}$ | $ \ket{011}$ | $-$ | $+$ |
| $X _1 $ | $ \ket{010}$ | $ \ket{101}$ | $-$ | $-$ |
| $X _2 $ | $ \ket{001}$ | $ \ket{110}$ | $+$ | $-$ |

したがって、2つの測定値の結果によって、どのビットフリップエラーが発生したかが一意に判断されますが、エンコードされた状態に関する情報は表示されません。
これらの結果を*より隣人*と呼びます。また、より隣人を*復旧*の原因となったエラーにマッピングするプロセスについても説明します。
特に、回復は、発生したより隣人を入力として受け取り、発生した可能性のあるエラーを修正する方法の処方箋を返す、*古典*的な推定手順であることを強調しています。

> [!NOTE]
> 上記のビットフリップコードは、シングルビットフリップエラーに対してのみ修正できます。つまり、1つの qubit に対して動作する `X` 操作です。
> 複数の qubit に `X` を適用すると、回復後に $ \ket{\overline{0}} $ が $ \ket{\overline{1}} $ にマップされます。
> 同様に、フェーズフリップ演算 `Z` を適用すると、$ \ket{\overline{1}} $ が $-\ket{\overline{1}} $ にマップされるため、$ \ket{\overline{+}} $ が $ \ket{\overline{-}} $ にマップされます。
> 一般的には、コードを作成して、より多くのエラーを処理したり、$ errors $Z 処理したり、$ errors を $X したりすることができます。

すべてのコード状態で同じように動作するクォンタムエラー修正の測定値を記述できるという洞察は、安定板の*形式*の essense です。
Q # キャノンは、安定板のコードに対してエンコードを記述し、それをエラーからどのように回復するかを説明するためのフレームワークを提供します。
このセクションでは、このフレームワークとそのアプリケーションについて、いくつかの単純なクォンタムエラー修正コードについて説明します。

> [!TIP]
> 安定板形式の詳細については、このセクションでは説明しません。
> [Gottesman 2009](https://arxiv.org/abs/0904.2557)の詳細については、読者を参照してください。

## <a name="representing-error-correcting-codes-in-q"></a>Q でのエラー修正コードの表現# ##

エラー修正コードを指定するために、Q # キャノンには、さまざまなユーザー定義型が用意されています。

- <xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`: は、qubits のレジスタをエラー修正コードのコードブロックとして解釈する必要があることを示します。
- <xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`: 測定結果の配列は、コードブロックで計測されたより隣人として解釈される必要があることを示します。
- <xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`:*従来*の関数を使用してより隣人を解釈し、適用する必要がある修正を返すことを示します。
- <xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`: エラー修正コードのコードブロックを生成するために、操作がデータを表す qubits を新しい ancilla qubits と共に受け取ることを示します。
- <xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`: より隣人情報を表すために使用されるデータ qubits と ancilla qubits にコードを修正するコードブロックを分解されする操作を表します。
- <xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`: コードブロックからより隣人情報を抽出するために使用する必要がある操作を表します。コードによって保護されている状態には支障がありません。

最後に、キャノンのエラー修正コードを定義するために必要なその他の型を収集するために、<xref:microsoft.quantum.errorcorrection.qecc> の種類が提供されています。 各安定板クォンタムコードに関連付けられているコードの長さは $n $、論理 qubits の数 $k $、および最小距離 $d $ で、多くの場合、⟦ $n $、$k $、$d $ ⟧の表記でグループ化します。 たとえば、<xref:microsoft.quantum.errorcorrection.bitflipcode> 関数は、⟦ 3, 1, 1 ⟧ビットフリップコードを定義します。

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

`QECC` の種類に復旧機能が含ま*れていない*ことに注意してください。
これにより、コード自体の定義を変更することなく、エラーの修正に使用される復旧関数を変更できます。この機能は特に、復旧によって想定されるモデルに特性測定のフィードバックを組み込む場合に便利です。

この方法でコードを定義すると、<xref:microsoft.quantum.errorcorrection.recover> 操作を使用してエラーから回復できます。

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

この詳細については、「[ビットフリップコードサンプル](https://github.com/Microsoft/Quantum/tree/master/Samples/src/BitFlipCode)」を参照してください。

ビットフリップコードとは別に、Q # キャノンは、 [5 桁の完全なコード](https://arxiv.org/abs/1305.08)と7つの[qubit コード](https://arxiv.org/abs/quant-ph/9705052)の実装によって提供されます。どちらの場合も、任意のシングル qubit エラーを修正できます。
