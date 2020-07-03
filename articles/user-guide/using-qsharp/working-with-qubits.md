---
title: 量子ビットの操作
description: 説明の入力
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 1655d18ab9d8638ad356e6fb90994b5c1fd76a25
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885295"
---
# <a name="working-with-qubits"></a>量子ビットの操作

Qubits は、クォンタムコンピューティングにおける情報の基本的なオブジェクトです。 Qubits の概要については、「[クォンタムコンピューティングについ](xref:microsoft.quantum.overview.understanding)て」を参照してください。また、数学表現の詳細については、「 [qubits](xref:microsoft.quantum.concepts.qubit)」を参照してください。 

この記事では、Q # プログラムで qubits を使用して操作する方法について説明します。 

> [!IMPORTANT]
>この記事で説明されているどのステートメントも、関数の本体内では有効ではありません。 これらは、操作内でのみ有効です。

## <a name="allocating-qubits"></a>割り当て (Qubits を)

物理 qubits は、quantum コンピューターの貴重なリソースであるため、コンパイラのジョブの一部として、それらが可能な限り効率的に使用されていることを確認する必要があります。
そのため、特定のステートメントブロック内で使用するために qubits を*割り当てる*には、Q # に指示する必要があります。
Qubits を1つの qubits として割り当てることも、*レジスタ*と呼ばれる qubits の配列として割り当てることもできます。 

### <a name="clean-qubits"></a>Clean qubits

ステートメントを使用して、 `using` ステートメントブロック中に使用する新しい qubits を割り当てます。

ステートメントは、キーワードと、 `using` その後にかっこで囲まれたバインディング `( )` と、qubits が使用可能なステートメントブロックで構成されます。
バインディングは、ステートメントと同じパターンに従い `let` ます。1つの記号または記号の組、等号 (= `=` )、1つの値、または*初期化子*の一致するタプルのいずれかです。

初期化子は、として指定された1つの qubit、 `Qubit()` または qubit の配列 (は式) に対して使用でき `Qubit[n]` `n` `Int` ます。
例:

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

この方法で割り当てられた qubits は、$ \ket {0} $ 状態から開始されます。 したがって、前の例で `auxiliary` は、は、状態が $ \ket $ である1つの qubit で、 {0} `register` 5 つの qubit 状態は $ \ket {00000} = \ket/ {0} otimes \ket/ {0} otimes/cドット/otimes \ket {0} $ です。
ブロックの末尾に `using` は、そのブロックによって割り当てられたすべての qubits がすぐに割り当て解除され、それ以上使用することはできません。

> [!WARNING]
> ターゲットコンピューターは、割り当て解除された qubits を再利用し、割り当てのために他のブロックに提供でき `using` ます。 そのため、ターゲットコンピューターでは、割り当て解除の直前に、qubits が $ \ket $ 状態にあることを想定してい {0} ます。
> 可能な場合は常に、ユニタリ操作を使用して、割り当てられた qubits を $ \ket $ に返し {0} ます。
> 必要に応じて、操作を使用できます @"microsoft.quantum.intrinsic.reset" 。この操作では、演算子を {0} 測定し、結果に基づいて条件付きで演算を実行することで、qubit を $ \ket $ に返します。 このような測定値は、残りの qubits を使用して結び付き破棄し、計算に影響を与える可能性があります。


### <a name="borrowed-qubits"></a>借りた Qubits

ステートメントを使用して `borrowing` 、一時的な使用のために qubits を割り当てます。これは、特定の状態である必要はありません。

計算時には、借りた qubits をスクラッチ領域として使用できます。
これらの qubits は、一般にクリーンな状態ではありません。つまり、$ \ket $ などの既知の状態で初期化されるとは限りません {0} 。
これらの状態は不明であるため、クォンタムコンピューターのメモリの他の部分との間でも、これらは "ダーティな" qubits と呼ばれることがよくあります。

バインディングは、ステートメントと同じパターンおよび規則に従い `using` ます。
例:
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
借用した qubits は不明な状態であり、ステートメントブロックの最後でスコープ外に出ます。
借り手は、借用したときと同じ状態で qubits を離れるようにコミットします。つまり、ステートメントブロックの先頭と末尾の状態は同じである必要があります。
この状態は必ずしも従来の状態ではないため、ほとんどの場合、スコープには測定値を含めないでください。 

Qubits を借りている場合、システムはまず、使用中であるが、ステートメントの本体ではアクセスされていない qubits から要求を入力しようとし `borrowing` ます。
このような qubits が不足している場合は、新しい qubits を割り当てて要求を完了します。

ダーティ qubits の既知のユースケースの中では、incrementers の少数の qubits と実装のみを必要とする、マルチ制御の CNOT ゲートの実装があります。
Q # での使用例については、この記事の「[貸し出し Qubits の例](#borrowing-qubits-example)」を参照するか、 [*2n + 2 Qubits と Toffoli ベースのモジュール乗算 (Based*](https://arxiv.org/abs/1611.07995) 、roetteler、および svore 2017) を使用して、借り qubits を利用するアルゴリズムについてのホワイトペーパーを参照してください。

## <a name="intrinsic-operations"></a>組み込みの操作

割り当てられると、関数と操作に qubit を渡すことができます。
ある意味では、これは、実行可能なアクションがすべて操作として定義されているため、Q # プログラムが qubit を使用して実行できることです。

この記事では、qubits との対話に使用できるいくつかの便利な Q # 操作について説明します。
これらおよび他の詳細については、「[組み込みの操作と関数](xref:microsoft.quantum.libraries.standard.prelude)」を参照してください。 

1つ目の方法として、1つの $Z $、$Y $、および $ $X、 [`X`](xref:microsoft.quantum.intrinsic.x) それぞれが型を持つ組み込みの操作、、およびによって Q # で表され [`Y`](xref:microsoft.quantum.intrinsic.y) [`Z`](xref:microsoft.quantum.intrinsic.z) `(Qubit => Unit is Adj + Ctl)` ます。

「組み込みの[操作と関数](xref:microsoft.quantum.libraries.standard.prelude)」で説明されているように、$ $X `X` は、ビットフリップ演算または NOT gate として考えられます。
操作を使用して、 `X` $ \ket{s_0 s_1 \ ドット s_n} $ の形式の状態を準備できます。これは、一部のクラシックビット文字列 $s $:

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> 後で、手動による制御フローを必要としない、この操作をよりコンパクトな方法で作成できます。

また、\Ket transform $H $ を使用して、$ \ket{+} = \ left (\ket {0} + \ket, {1} right)/\ sqrt {2} $ および $ \ket {-} = \ left (\ket-Hadamard/right)//sqrt $ などの状態を準備することもできます {0} {1} {2} 。これは、組み込み> の操作によって Q # で表され [`H`](xref:microsoft.quantum.intrinsic.h) ます。

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>測定

個々の qubits の測定は、 [Bloch 球の p](xref:microsoft.quantum.glossary#bloch-sphere)li 軸によって表される異なるベースで実行できます。
*計算基準*はベースを指し、 `PauliZ` 測定に最も一般的に使用されます。

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a>1つの qubit を基準にして測定する `PauliZ`

演算を使用します [`M`](xref:microsoft.quantum.intrinsic.m) 。この操作は組み込みの非イン数値演算であり、1つの qubit を `PauliZ` 基準にして、その結果に古典的な値を割り当てます。
`M`には、予約された戻り値の型があります `Result` 。これは、値を取得するか、測定された `Zero` `One` 状態 $ \ket {0} $ または $ \ket $-に対応します。これは、 {1} 結果がクォンタムの状態ではなくなったことを示します。

単純な例として、次の操作があります。この操作では、$ \ket $ 状態に1つの qubit が割り当てられ、 {0} Hadamard 操作が適用され、その `H` 結果が基になり `PauliZ` ます。

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a>特定のベースの1つ以上の qubits を測定する

特定のベースの1つ以上の qubits の配列を測定するには、操作を使用し [`Measure`](xref:microsoft.quantum.intrinsic.measure) ます。

への入力 `Measure` は `Pauli` 、型 (たとえば、) の配列で `[PauliX, PauliZ, PauliZ]` あり、qubits の配列です。

次の演算では、より複雑な例が示されています。この操作では、 `true` 型のレジスタ内のすべての qubits が、指定された pare によって測定された場合は、ブール値を返し、それ以外の場合は `Qubit[]` を返し `false` ます。

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

この例では、一度 `Measure` に1つずつ個別の qubits に対してのみが実行されることに注意してくださいが、この操作は複数の qubits の結合測定に拡張できます。

## <a name="borrowing-qubits-example"></a>借りた Qubits の例

次の関数のように、キーワードを使用するキャノンの例があり `borrowing` `MultiControlledXBorrow` ます。 が `controls` 操作に追加する制御 qubits を `X` 示す場合、この実装によって追加されるダーティ[ancillas](xref:microsoft.quantum.glossary#ancilla)の数はに `Length(controls)-2` なります。

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

この例では、連結子の広範な使用を、 `With` adjoint をサポートする操作 (など) に適用できる形式で使用して `WithA` います。
これは、 `With` 内部操作にのみ制御を反映する構造体にコントロールを追加するため、適切なプログラミングスタイルです。
また、操作のに加えて、操作の本体の実装が明示的に指定されていることにも注意してください。これは、 `body` `controlled` ステートメントを実行するのでは `controlled auto` ありません。
その理由は、回線の構造により、コントロールをさらに追加するのは簡単です。これは、内の各ゲートにコントロールを追加する場合と比べて便利です `body` 。 

このコードを別のキャノン関数と比較して、 `MultiControlledXClean` 乗算制御演算を実装するのと同じ目標を達成し `X` ます。ただし、メカニズムを使用していくつかの clean qubits を使用し `using` ます。 

## <a name="next-steps"></a>次の手順

Q # の[制御フロー](xref:microsoft.quantum.guide.controlflow)について説明します。