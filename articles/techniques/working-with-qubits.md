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
# <a name="working-with-qubits"></a><span data-ttu-id="6fc13-103">Qubits の操作</span><span class="sxs-lookup"><span data-stu-id="6fc13-103">Working with Qubits</span></span>

<span data-ttu-id="6fc13-104">Q # 言語のさまざまな部分を見てきましたが、それについて説明し、qubits 自体を使用する方法を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="6fc13-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="6fc13-105">割り当て (Qubits を)</span><span class="sxs-lookup"><span data-stu-id="6fc13-105">Allocating Qubits</span></span>

<span data-ttu-id="6fc13-106">まず、Q # で使用できる qubit を取得するために、`using` ブロック内に qubit を*割り当て*ます。</span><span class="sxs-lookup"><span data-stu-id="6fc13-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="6fc13-107">この方法で割り当てられた qubits は、$ \ket{0}$ state; から開始されます。上の例では、`register` は状態が $ \ket{00000} = \ket{0}/otimes \ket{0}/otimes/cドット/otimes \ket{0}$ になります。</span><span class="sxs-lookup"><span data-stu-id="6fc13-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="6fc13-108">`using` ブロックの最後には、そのブロックによって割り当てられたすべての qubits がすぐに割り当て解除され、それ以上使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6fc13-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="6fc13-109">ターゲットコンピューターでは、割り当てのために再利用して他の `using` ブロックに提供できるように、割り当て解除の直前に qubits が $ \ket{0}$ 状態にあることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="6fc13-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="6fc13-110">可能な場合は常に、ユニタリ操作を使用して、割り当てられた qubits を $ \ket{0}$ に返します。</span><span class="sxs-lookup"><span data-stu-id="6fc13-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="6fc13-111">必要に応じて、@"microsoft.quantum.intrinsic.reset" 操作を使用して qubit を測定し、測定結果を使用して、測定された qubit が $ \ket{0}$ に返されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="6fc13-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="6fc13-112">このような測定値は、残りの qubits を使用してすべての entangを破棄するため、計算に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6fc13-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="6fc13-113">組み込みの操作</span><span class="sxs-lookup"><span data-stu-id="6fc13-113">Intrinsic Operations</span></span>

<span data-ttu-id="6fc13-114">割り当てられた後、qubit を関数と操作に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="6fc13-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="6fc13-115">ある意味では、これは、実行可能なアクションがすべて操作として定義されているため、Q # プログラムが qubit を使用して実行できることです。</span><span class="sxs-lookup"><span data-stu-id="6fc13-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="6fc13-116">これらの操作については、[組み込みの操作と関数](xref:microsoft.quantum.libraries.standard.prelude)で詳しく説明しますが、ここでは、qubits との対話に使用できるいくつかの便利な操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="6fc13-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="6fc13-117">1つ目の方法として、1つの $Z $、$Y $、および $ $X、それぞれが型 `Y`を持つ組み込み操作 `X`、`Z`、および `(Qubit => Unit is Adj + Ctl)`によって Q # で表されます。</span><span class="sxs-lookup"><span data-stu-id="6fc13-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="6fc13-118">「組み込みの[操作と関数](xref:microsoft.quantum.libraries.standard.prelude)」で説明されているように、$X $ と `X` はビットフリップ演算または NOT gate と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="6fc13-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="6fc13-119">`X` 操作を使用すると、いくつかのクラシックビット文字列 $s $: の形式で $ \ket{s_0 s_1、ドット s_n} $ を準備できます。</span><span class="sxs-lookup"><span data-stu-id="6fc13-119">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="6fc13-120">後で、手動によるフロー制御を必要としない、この操作を記述するよりコンパクトな方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="6fc13-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="6fc13-121">また、組み込みの操作によって Q # で表される \Ket transform{0} $ を使用して、$ \ket{+} = \ left (\ket{0} + \ket{1}/\ sqrt{2}$ と $ \ket{-} =-left (\ket{1}-Hadamard{2}-right)//sqrt $H $ などの状態を準備することもできます。</span><span class="sxs-lookup"><span data-stu-id="6fc13-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="6fc13-122">測定</span><span class="sxs-lookup"><span data-stu-id="6fc13-122">Measurements</span></span>

<span data-ttu-id="6fc13-123">組み込みの非インサム演算である `Measure` 操作を使用すると、`Qubit` 型のオブジェクトから古典的な情報を抽出し、`Result`予約済みの型を持つ古典的な値を結果として割り当てることができます。これは、結果がクォンタム状態ではなくなっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="6fc13-123">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="6fc13-124">`Measure` への入力は、Bloch 球の p Li 軸で、型 `Pauli` (たとえば、`PauliX`) の値と `Qubit`型の値で表されます。</span><span class="sxs-lookup"><span data-stu-id="6fc13-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="6fc13-125">単純な例として、次の操作があります。この操作では、$ \ket{0}$ state に1つの qubit が割り当てられ、Hadamard operation `H` が適用され、その結果が `PauliZ` ベースで計測されます。</span><span class="sxs-lookup"><span data-stu-id="6fc13-125">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="6fc13-126">さらに複雑な例として、次の演算では、`Qubit[]` 型のレジスタ内のすべての qubits が、指定された Pare によって測定された場合は0になり、それ以外の場合は `false` を返す場合に `true` ブール値が返されます。</span><span class="sxs-lookup"><span data-stu-id="6fc13-126">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="6fc13-127">Q # 言語を使用すると、古典制御フローは qubits の測定結果に依存することになります。</span><span class="sxs-lookup"><span data-stu-id="6fc13-127">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="6fc13-128">この機能により、確率論的を実装するためのコンピューティングコストを削減できる強力なガジェットを実装できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6fc13-128">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="6fc13-129">例として、Q # では、いわゆる*繰り返し-成功*(ru) のパターンを簡単に実装できます。</span><span class="sxs-lookup"><span data-stu-id="6fc13-129">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="6fc13-130">これらの RU パターンは、基本ゲートの観点から*予想*低コストの確率論的プログラムですが、実際のコストは、考えられるさまざまな branchings の実際の実行と実際のインターリーブによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6fc13-130">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="6fc13-131">Repeat To Success (RU) パターンを容易にするために、Q # はコンストラクトをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6fc13-131">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

<span data-ttu-id="6fc13-132">ここで `statementBlock1` と `statementBlock2` は0個以上の Q # ステートメントであり、`Bool`型の値に評価される有効な式を `expression` します。</span><span class="sxs-lookup"><span data-stu-id="6fc13-132">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="6fc13-133">一般的なユースケースでは、次の Q # 操作は、Bloch 球の $ (I + 2i Z)/\ sqrt{5}$ の無理数軸を中心とした回転を実装します。</span><span class="sxs-lookup"><span data-stu-id="6fc13-133">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="6fc13-134">これは、既知の RUS パターンを使用して実現されます。</span><span class="sxs-lookup"><span data-stu-id="6fc13-134">This is accomplished by using a known RUS pattern:</span></span>

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

<span data-ttu-id="6fc13-135">この例では、変更可能な変数 `finished` の使用方法を示しています。これは、反復処理までの繰り返しループ全体のスコープ内にあり、ループの前に初期化され、フィックスアップのステップで更新されます。</span><span class="sxs-lookup"><span data-stu-id="6fc13-135">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="6fc13-136">最後に、"$ \ket{+} $" 状態から開始して、クォンタムの状態を準備する RU パターンの例を示します。これには、(\ sqrt{2}\ket{0}+ \ket{1}-right) $ というクォンタムの{3}{1}状態が用意されています。</span><span class="sxs-lookup"><span data-stu-id="6fc13-136">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="6fc13-137">[標準ライブラリで提供されている単体テストのサンプル](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)も参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fc13-137">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

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

<span data-ttu-id="6fc13-138">この操作に示されている注目すべきプログラム機能は、ループのより複雑な `fixup` の部分です。これには、クォンタム操作が含まれます。また、`AssertProb` ステートメントを使用して、プログラム内の特定の特定のポイントでクォンタムの状態を測定する確率を確認します。</span><span class="sxs-lookup"><span data-stu-id="6fc13-138">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="6fc13-139">[`Assert`](xref:microsoft.quantum.intrinsic.assert)と[`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob)操作の詳細については、「[テストおよびデバッグ](xref:microsoft.quantum.techniques.testing-and-debugging)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fc13-139">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>
