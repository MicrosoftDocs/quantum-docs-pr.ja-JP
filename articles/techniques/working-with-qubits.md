---
title: Qubits の操作
description: 'Qubits の使用-Q # 手法'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: dc6db93dadc37534aece9624fe516125d919f8cd
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819996"
---
# <a name="working-with-qubits"></a>Qubits の操作

Q # 言語のさまざまな部分を見てきましたが、それについて説明し、qubits 自体を使用する方法を見てみましょう。

## <a name="allocating-qubits"></a>割り当て (Qubits を)

まず、Q # で使用できる qubit を取得するために、`using` ブロック内に qubit を*割り当て*ます。

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

この方法で割り当てられた qubits は、$ \ket{0}$ state; から開始されます。上の例では、`register` は状態が $ \ket{00000} = \ket{0}/otimes \ket{0}/otimes/cドット/otimes \ket{0}$ になります。
`using` ブロックの最後には、そのブロックによって割り当てられたすべての qubits がすぐに割り当て解除され、それ以上使用することはできません。

> [!WARNING]
> ターゲットコンピューターでは、割り当てのために再利用して他の `using` ブロックに提供できるように、割り当て解除の直前に qubits が $ \ket{0}$ 状態にあることを想定しています。
> 可能な場合は常に、ユニタリ操作を使用して、割り当てられた qubits を $ \ket{0}$ に返します。
> 必要に応じて、@"microsoft.quantum.intrinsic.reset" 操作を使用して qubit を測定し、測定結果を使用して、測定された qubit が $ \ket{0}$ に返されるようにすることができます。 このような測定値は、残りの qubits を使用してすべての entangを破棄するため、計算に影響を与える可能性があります。

## <a name="intrinsic-operations"></a>組み込みの操作

割り当てられた後、qubit を関数と操作に渡すことができます。
ある意味では、これは、実行可能なアクションがすべて操作として定義されているため、Q # プログラムが qubit を使用して実行できることです。
これらの操作については、[組み込みの操作と関数](xref:microsoft.quantum.libraries.standard.prelude)で詳しく説明しますが、ここでは、qubits との対話に使用できるいくつかの便利な操作について説明します。

1つ目の方法として、1つの $Z $、$Y $、および $ $X、それぞれが型 `Y`を持つ組み込み操作 `X`、`Z`、および `(Qubit => Unit is Adj + Ctl)`によって Q # で表されます。
「組み込みの[操作と関数](xref:microsoft.quantum.libraries.standard.prelude)」で説明されているように、$X $ と `X` はビットフリップ演算または NOT gate と考えることができます。
`X` 操作を使用すると、いくつかのクラシックビット文字列 $s $: の形式で $ \ket{s_0 s_1、ドット s_n} $ を準備できます。

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

また、組み込みの操作によって Q # で表される \Ket transform{0} $ を使用して、$ \ket{+} = \ left (\ket{0} + \ket{1}/\ sqrt{2}$ と $ \ket{-} =-left (\ket{1}-Hadamard{2}-right)//sqrt $H $ などの状態を準備することもできます。

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

組み込みの非インサム演算である `Measure` 操作を使用すると、`Qubit` 型のオブジェクトから古典的な情報を抽出し、`Result`予約済みの型を持つ古典的な値を結果として割り当てることができます。これは、結果がクォンタム状態ではなくなっていることを示します。
`Measure` への入力は、Bloch 球の p Li 軸で、型 `Pauli` (たとえば、`PauliX`) の値と `Qubit`型の値で表されます。

単純な例として、次の操作があります。この操作では、$ \ket{0}$ state に1つの qubit が割り当てられ、Hadamard operation `H` が適用され、その結果が `PauliZ` ベースで計測されます。

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

さらに複雑な例として、次の演算では、`Qubit[]` 型のレジスタ内のすべての qubits が、指定された Pare によって測定された場合は0になり、それ以外の場合は `false` を返す場合に `true` ブール値が返されます。

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

Q # 言語を使用すると、古典制御フローは qubits の測定結果に依存することになります。
この機能により、確率論的を実装するためのコンピューティングコストを削減できる強力なガジェットを実装できるようになります。
例として、Q # では、いわゆる*繰り返し-成功*(ru) のパターンを簡単に実装できます。
これらの RU パターンは、基本ゲートの観点から*予想*低コストの確率論的プログラムですが、実際のコストは、考えられるさまざまな branchings の実際の実行と実際のインターリーブによって異なります。

Repeat To Success (RU) パターンを容易にするために、Q # はコンストラクトをサポートしています。

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

ここで `statementBlock1` と `statementBlock2` は0個以上の Q # ステートメントであり、`Bool`型の値に評価される有効な式を `expression` します。
一般的なユースケースでは、次の Q # 操作は、Bloch 球の $ (I + 2i Z)/\ sqrt{5}$ の無理数軸を中心とした回転を実装します。 これは、既知の RUS パターンを使用して実現されます。

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

この例では、変更可能な変数 `finished` の使用方法を示しています。これは、反復処理までの繰り返しループ全体のスコープ内にあり、ループの前に初期化され、フィックスアップのステップで更新されます。

最後に、"$ \ket{+} $" 状態から開始して、クォンタムの状態を準備する RU パターンの例を示します。これには、(\ sqrt{2}\ket{0}+ \ket{1}-right) $ というクォンタムの{3}{1}状態が用意されています。
[標準ライブラリで提供されている単体テストのサンプル](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)も参照してください。

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

この操作に示されている注目すべきプログラム機能は、ループのより複雑な `fixup` の部分です。これには、クォンタム操作が含まれます。また、`AssertProb` ステートメントを使用して、プログラム内の特定の特定のポイントでクォンタムの状態を測定する確率を確認します。
[`Assert`](xref:microsoft.quantum.intrinsic.assert)と[`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob)操作の詳細については、「[テストおよびデバッグ](xref:microsoft.quantum.techniques.testing-and-debugging)」も参照してください。
