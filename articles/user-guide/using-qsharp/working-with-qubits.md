---
title: 量子ビットの操作
description: 説明の入力
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: e89b9ccfe2a0796e01eedfc99f7ce71038d85f38
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430936"
---
# <a name="working-with-qubits"></a>量子ビットの操作

Q # 言語のさまざまな部分を見てきましたが、それについて説明し、qubits 自体を使用する方法を見てみましょう。

関数の本体内では、これらのステートメントを使用できないことに注意してください。
これらは、操作内でのみ有効です。

## <a name="allocating-qubits"></a>割り当て (Qubits を)

### <a name="clean-qubits"></a>Clean qubits

ステートメント `using` は、ステートメントブロック中に使用する新しい qubits を*割り当てる*ために使用されます。

このステートメントは、キーワードと、その `using` 後に始めかっこ `(` 、バインド、終わりかっこ `)` 、および qubits を使用できるようにするステートメントブロックで構成されます。
バインディングは、ステートメントと同じパターンに従い `let` ます。1つの記号または記号の組、等号 (= `=` )、1つの値、または*初期化子*の一致するタプルのいずれかです。

初期化子は、として指定された1つの qubit、 `Qubit()` または qubit の配列 (は式) に対して使用でき `Qubit[n]` `n` `Int` ます。
たとえば、オブジェクトに適用された

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

この方法で割り当てられた qubits は、$ \ket {0} $ 状態から開始されます。上記の例では、この `register` 状態は $ \ket {00000} = \ket/ {0} otimes \ket/ {0} otimes/cドット/otimes \ket {0} $ です。
ブロックの末尾に `using` は、そのブロックによって割り当てられたすべての qubits がすぐに割り当て解除され、それ以上使用することはできません。

> [!WARNING]
> ターゲットコンピューターでは {0} 、割り当てのために再利用して他のブロックに提供できるように、割り当て解除の直前に qubits が $ \ket $ 状態にあることを想定してい `using` ます。
> 可能な場合は常に、ユニタリ操作を使用して、割り当てられた qubits を $ \ket $ に返し {0} ます。
> 必要に応じて、 @"microsoft.quantum.intrinsic.reset" 操作を使用して qubit を測定し、測定結果を使用して、測定された qubit が $ \ket $ に返されるようにすることができ {0} ます。 このような測定値は、残りの qubits を使用してすべての entangを破棄するため、計算に影響を与える可能性があります。


### <a name="borrowed-qubits"></a>借りた Qubits

この `borrowing` ステートメントは、特定の状態にする必要がない、一時的な使用に対して qubits を使用できるようにするために使用されます。

借用機構を使用すると、計算中にスクラッチ領域として使用できる qubits を割り当てることができます。
通常、これらの qubits はクリーンな状態ではありません。つまり、$ \ket $ などの既知の状態で初期化されるとは限りません。 {0}
これらの状態は不明であるため、クォンタムコンピューターのメモリの他の部分との間でも、これらは "ダーティな" qubits と呼ばれることがよくあります。

バインドは、ステートメントと同じパターンおよび規則に従い `using` ます。
たとえば、オブジェクトに適用された
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
借用した qubits は不明な状態であり、ステートメントブロックの最後でスコープ外に出ます。
借り手は、貸し出しされたときと同じ状態に qubits を残すことをコミットします。つまり、ステートメントブロックの先頭と末尾の状態は同じであると想定されます。
特に、この状態は必ずしも古典的な状態ではありません。ほとんどの場合、借りているスコープには測定値を含めないでください。 

Qubits を借りている場合、システムはまず、使用中であるが、ステートメントの本体ではアクセスされていない qubits から要求を入力しようとし `borrowing` ます。
このような qubits が不足している場合は、要求を完了するために新しい qubits が割り当てられます。


ダーティ qubits の既知のユースケースの中では、incrementers の少数の qubits と実装のみを必要とする、マルチ制御の CNOT ゲートの実装があります。
次の[例](#borrowing-qubits-example)を参照して Q # での使用例をご覧ください。または、借り qubits を利用するアルゴリズムに対して、 [*2n + 2 Qubits と Toffoli ベースのモジュール乗算 2017 (ベースのモジュール乗算) を使用してファクタリング*](https://arxiv.org/abs/1611.07995)したホワイトペーパーを参照してください。


## <a name="intrinsic-operations"></a>組み込みの操作

割り当てられた後、qubit を関数と操作に渡すことができます。
ある意味では、これは、実行可能なアクションがすべて操作として定義されているため、Q # プログラムが qubit を使用して実行できることです。
これらの操作については、[組み込みの操作と関数](xref:microsoft.quantum.libraries.standard.prelude)で詳しく説明しますが、ここでは、qubits との対話に使用できるいくつかの便利な操作について説明します。

1つ目の方法として、1つの $Z $、$Y $、および $ $X、 `X` それぞれが型を持つ組み込みの操作、、およびによって Q # で表され `Y` `Z` `(Qubit => Unit is Adj + Ctl)` ます。
「組み込みの[操作と関数](xref:microsoft.quantum.libraries.standard.prelude)」で説明されているように、$X $ として、がビットフリップ演算であるか、そうではないと考えることができ `X` ます。
この操作を実行すると、 `X` いくつかのクラシックビット文字列 $s $: で $ \ket{s_0 s_1 \ ドット s_n} $ という形式の状態を準備できます。

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
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> 後で、手動によるフロー制御を必要としない、この操作を記述するよりコンパクトな方法を紹介します。

また、 {0} {1} {2} {-} {0} {1} {2} 組み込み操作によって Q # で表される \ket transform $H $ を使用して、$ \ket{+} = \ left (\ket + \ket →)/\ sqrt $ および $ \ket = \ left (\ket-Hadamard/right)/\ sqrt $ などの状態を準備することもでき `H : (Qubit => Unit is Adj + Ctl)` ます。

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>測定

組み込みの非インサム演算である操作を使用する `Measure` と、型のオブジェクトから古典的な情報を抽出し、その結果 `Qubit` として古典的な値を割り当てることができます。これには予約済みの型があり、結果はクォンタム状態ではなくなっていることを `Result` 示します。
への入力 `Measure` は、Bloch 球の p li 軸で、型 `Pauli` (たとえば、) の値 `PauliX` と型の値で表され `Qubit` ます。

単純な例として、次の操作があります。この操作では、$ \ket $ 状態に1つの qubit が割り当てられ、 {0} Hadamard 操作が適用され、その `H` 結果が基になり `PauliZ` ます。

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

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

## <a name="borrowing-qubits-example"></a>借りた Qubits の例

キャノンには、キーワードを使用する例があり `borrowing` ます。たとえば、 `MultiControlledXBorrow` 次に定義されている関数です。
は、 `controls` 操作に追加する必要があるコントロール qubits を示す場合 `X` 、 `Length(controls)-2` この実装によって多くのダーティ ancillas の全体が追加されます。

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

結合子は、 `With` adjoint をサポートする操作 (つまり、 `WithA` この例では---されています) に適用される---の形式で広く使用されていることに注意してください。
これは、 `With` 内部操作にのみ制御を反映する構造体にコントロールを追加するため、適切なプログラミングスタイルです。
さらに、ここでは、操作のに加えて、操作の本体の実装が明示的に指定されていることに注意してください。これは、ステートメントを再実行することで `body` `controlled` は `controlled auto` ありません。
その理由は、の各ゲートにコントロールを追加する場合と比較して、役に立つコントロールをさらに簡単に追加する方法です `body` 。 

このコードを別のキャノン関数と比較して、 `MultiControlledXClean` 乗算制御演算を実装するのと同じ目標を達成し `X` ます。ただし、メカニズムを使用していくつかの clean qubits を使用し `using` ます。 

## <a name="whats-next"></a>次の課題
Q # の[制御フロー](xref:microsoft.quantum.guide.controlflow)について説明します。