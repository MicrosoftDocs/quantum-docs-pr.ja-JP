---
title: 標準ライブラリでのエラー修正 Q#
description: プログラムでエラー修正コードを使用し Q# ながら、qubits の状態を保護する方法について説明します。
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: dad0db4d2aab27e5ae46d4df10ee050f785d8bb8
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835555"
---
# <a name="error-correction"></a>エラーの修正 #

## <a name="introduction"></a>はじめに ##

従来のコンピューティングでは、エラーに対して1つの保護が必要な場合は、データビットを繰り返すことによって、そのビットを *論理ビット* で表現するのが十分な場合があります。
たとえば、$0 $ > は、 {0} データビット0のエンコーディングとして使用します。この場合、ラベル0の上の行を使用して、0状態のビットのエンコーディングであることを示します。
同様に $/の前に {1} = $111 がある場合は、1つのビットフリップエラーから保護する単純な繰り返しコードが用意されています。
つまり、3つのビットのいずれかが反転されている場合は、過半数の投票を行って論理ビットの状態を復旧できます。
古典的なエラー修正は、この特定の例 ( [コード理論の概要を説明する](https://www.springer.com/us/book/9783540641339)ことをお勧めします) の方がはるかに豊富ですが、上記の繰り返しコードでは、クォンタム情報の保護に関する問題が既に考えられています。
つまり、 [複製なしの定理](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) は、個々の qubit を測定して、上記の古典的なコードと比較して大部分の投票を行うと、保護しようとしている正確な情報が失われていることを意味します。

[クォンタム] 設定には、測定値が問題であることが表示されます。 上記のエンコードを実装することもできます。
これを行うと、エラー修正をクォンタムケースに一般化する方法を確認することができます。
したがって、let $ \ket{\overline {0} } = \ket {000} = \ket {0} /otimes \ket、 {0} otimes \ket {0} $、let $ \ket{\overline {1} } = \ket {111} $。
次に、直線性により、すべての入力に対して繰り返しコードを定義しました。たとえば、$ \ket{\overline{+}} = (\ket{\overline {0} } + \ket{\overline {1} })/\ sqrt {2} = (\ket {000} + \ket {111} )/\ sqrt $ のように {2} なります。
具体的には、ビットフリップエラーによって、真ん中の qubit に対して _1 $ act $X します。両方の分岐で必要とされる修正が、正確には _1 $: $ $ \begin{align} X_1 \ket{\overline{+}} & = \ket ( {1} {2} X_1 + {000} X_1 \ket \ {111} ) $X \\ \\ & =-frac {1} {/sqrt {2} } \ left (\ket {010} + \ket/ {101} right) であることがわかります。
\end{align} $ $

保護しようとしている状態を測定せずにこの問題が発生していることを特定する方法を確認するには、それぞれのビットフリップエラーが論理的な状態にどのようになるかを記述することをお勧めします。

| エラー $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ |
| --- | --- | --- |
| $\boldone$ | $ \ket {000} $ | $ \ket {111} $ |
| $X_0$ | $ \ket {100} $ | $ \ket {011} $ |
| $X_1$ | $ \ket {010} $ | $ \ket {101} $ |
| $X_2$ | $ \ket {001} $ | $ \ket {110} $ |

エンコードされている状態を保護するためには、3つのエラーを相互に区別できる必要があります。また、$ \ket{\overline {0} } $ と $ \ket{\overline} $ を区別せずに、id $ > から id $ > を区別できるようにする必要があり {1} ます。
たとえば、$Z 0 $ を測定する場合、 {0} エラーなしのケースでは $ \ket{\overline} $ および $ \ket{\overline} $ に対して異なる結果が得られるため、はエンコードされた {1} 状態を折りたたみます。
一方、各計算基準の状態の最初の2ビットのパリティである $Z 0 Z_1 $ を測定することを検討してください。
Pauli 演算子の各測定値がどの eigenvalue に対応しているかを確認します。そのため、上の表の各州 $ \ket{\psi} $ では、$ \pm\ket{\psi} $ を取得するかどうかを確認するために、0 Z_1 \ket{\psi} $ $Z 計算できます。
$Z 0 Z_1 \ket {000} = \ket {000} $ で $Z 0 Z_1 \ket = \ket $ であることに注意して {111} ください。これにより、 {111} この測定では、エンコードされた両方の状態が同じであることが結論となります。
一方、$Z 0 Z_1 \ket {100} =-\ket {100} $ and $Z 0 Z_1 \ket {011} =-\ket {011} $ のように指定すると、0 $Z $ を測定した結果として、発生したエラーに関する有用な情報が示されます。

このことを強調するために、上記の表を繰り返しますが、各行に 0 Z_1 $ および $Z _1 Z_2 $ $Z 測定した結果を追加します。
各測定の結果は、 Q# `Result` それぞれとの値に対応する $ + $ または $-$ のいずれかの eigenvalue の符号によって示され `Zero` `One` ます。

| エラー $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ | $Z 0 Z_1 $ の結果 | $Z _1 Z_2 $ の結果 |
| --- | --- | --- | --- | --- |
| $\boldone$ | $ \ket {000} $ | $ \ket {111} $ | $+$ | $+$ |
| $X_0$ | $ \ket {100} $ | $ \ket {011} $ | $-$ | $+$ |
| $X_1$ | $ \ket {010} $ | $ \ket {101} $ | $-$ | $-$ |
| $X_2$ | $ \ket {001} $ | $ \ket {110} $ | $+$ | $-$ |

したがって、2つの測定値の結果によって、どのビットフリップエラーが発生したかが一意に判断されますが、エンコードされた状態に関する情報は表示されません。
これらの結果を *より隣人*と呼びます。また、より隣人を *復旧*の原因となったエラーにマッピングするプロセスについても説明します。
特に、回復は、発生したより隣人を入力として受け取り、発生した可能性のあるエラーを修正する方法の処方箋を返す、 *古典* 的な推定手順であることを強調しています。

> [!NOTE]
> 上記のビットフリップコードは、シングルビットフリップエラーに対してのみ修正できます。つまり、 `X` 1 つの qubit に対して動作する操作です。
> 複数の `X` qubit にを適用すると、 {0} 復旧後に $ \ket{\overline} $ が $ \ket{\overline} $ にマップされ {1} ます。
> 同様に、フェーズフリップ操作を適用する `Z` と $ \ket{\overline {1} } $ が $-\ket{\overline} $ にマップされる {1} ため、$ \ket{\overline{+}} $ が $ \ket{\overline} $ にマップされ {-} ます。
> 一般的には、コードを作成して、より多くのエラーを処理したり、$ errors $Z 処理したり、$ errors を $X したりすることができます。

すべてのコード状態で同じように動作するクォンタムエラー修正の測定値を記述できるという洞察は、安定板の *形式*の本質です。
キャノンは、 Q# 安定板のコードに対してエンコードを記述し、それをエラーからどのように回復するかを説明するためのフレームワークを提供します。
このセクションでは、このフレームワークとそのアプリケーションについて、いくつかの単純なクォンタムエラー修正コードについて説明します。

> [!TIP]
> 安定板形式の詳細については、このセクションでは説明しません。
> [Gottesman 2009](https://arxiv.org/abs/0904.2557)の詳細については、読者を参照してください。

## <a name="representing-error-correcting-codes-in-no-locq"></a>エラー修正コードを表す Q# ##

エラー修正コードを指定するために、 Q# キャノン社はいくつかの異なるユーザー定義型を提供しています。

- <xref:microsoft.quantum.errorcorrection.logicalregister>`= Qubit[]`: Qubits のレジスタは、エラー修正コードのコードブロックとして解釈される必要があることを示します。
- <xref:microsoft.quantum.errorcorrection.syndrome>`= Result[]`: 測定結果の配列を、コードブロックで測定されるより隣人として解釈する必要があることを示します。
- <xref:microsoft.quantum.errorcorrection.recoveryfn>`= (Syndrome -> Pauli[])`: より隣人を解釈し、適用する必要のある修正を返すために、*古典*関数を使用する必要があることを示します。
- <xref:microsoft.quantum.errorcorrection.encodeop>`= ((Qubit[], Qubit[]) => LogicalRegister)`: エラー修正コードのコードブロックを生成するために、操作がデータを表す qubits を新しい ancilla qubits と共に受け取ることを示します。
- <xref:microsoft.quantum.errorcorrection.decodeop>`= (LogicalRegister => (Qubit[], Qubit[]))`: データ qubits にコードを修正するコードブロックとより隣人情報を表すために使用される ancilla qubits を分解されする操作であることを示します。
- <xref:microsoft.quantum.errorcorrection.syndromemeasop>`= (LogicalRegister => Syndrome)`: コードブロックからより隣人情報を抽出するために使用する必要がある操作を表します。コードによって保護されている状態には支障がありません。

最後に、キャノンの <xref:microsoft.quantum.errorcorrection.qecc> エラー修正コードを定義するために必要な他の型を収集するための型を提供します。 各安定板クォンタムコードに関連付けられているコードの長さは $n $、論理 qubits の数 $k $、および最小距離 $d $ で、多くの場合、⟦ $n $、$k $、$d $ ⟧の表記でグループ化します。 たとえば、関数は、 <xref:microsoft.quantum.errorcorrection.bitflipcode> ⟦ 3, 1, 1 ⟧ビットフリップコードを定義します。

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

`QECC`型に復旧関数が含ま*れていない*ことに注意してください。
これにより、コード自体の定義を変更することなく、エラーの修正に使用される復旧関数を変更できます。この機能は特に、復旧によって想定されるモデルに特性測定のフィードバックを組み込む場合に便利です。

この方法でコードを定義すると、操作を使用して <xref:microsoft.quantum.errorcorrection.recover> エラーから回復できます。

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

この詳細については、「 [ビットフリップコードサンプル](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code)」を参照してください。

この例では、ビットフリップコード以外に、 Q# [5 qubit の完全なコード](https://arxiv.org/abs/quant-ph/9602019)と7つの [qubit コード](https://arxiv.org/abs/quant-ph/9705052)を実装しています。どちらも任意のシングル qubit エラーを修正できます。
