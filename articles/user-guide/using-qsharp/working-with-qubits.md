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
# <a name="working-with-qubits"></a><span data-ttu-id="e2dcd-103">量子ビットの操作</span><span class="sxs-lookup"><span data-stu-id="e2dcd-103">Working with qubits</span></span>

<span data-ttu-id="e2dcd-104">Q # 言語のさまざまな部分を見てきましたが、それについて説明し、qubits 自体を使用する方法を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

<span data-ttu-id="e2dcd-105">関数の本体内では、これらのステートメントを使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-105">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="e2dcd-106">これらは、操作内でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-106">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="e2dcd-107">割り当て (Qubits を)</span><span class="sxs-lookup"><span data-stu-id="e2dcd-107">Allocating Qubits</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="e2dcd-108">Clean qubits</span><span class="sxs-lookup"><span data-stu-id="e2dcd-108">Clean qubits</span></span>

<span data-ttu-id="e2dcd-109">ステートメント `using` は、ステートメントブロック中に使用する新しい qubits を*割り当てる*ために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-109">The `using` statement is used to *allocate* new qubits for use during a statement block.</span></span>

<span data-ttu-id="e2dcd-110">このステートメントは、キーワードと、その `using` 後に始めかっこ `(` 、バインド、終わりかっこ `)` 、および qubits を使用できるようにするステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-110">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="e2dcd-111">バインディングは、ステートメントと同じパターンに従い `let` ます。1つの記号または記号の組、等号 (= `=` )、1つの値、または*初期化子*の一致するタプルのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-111">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="e2dcd-112">初期化子は、として指定された1つの qubit、 `Qubit()` または qubit の配列 (は式) に対して使用でき `Qubit[n]` `n` `Int` ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-112">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="e2dcd-113">たとえば、オブジェクトに適用された</span><span class="sxs-lookup"><span data-stu-id="e2dcd-113">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="e2dcd-114">この方法で割り当てられた qubits は、$ \ket {0} $ 状態から開始されます。上記の例では、この `register` 状態は $ \ket {00000} = \ket/ {0} otimes \ket/ {0} otimes/cドット/otimes \ket {0} $ です。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-114">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="e2dcd-115">ブロックの末尾に `using` は、そのブロックによって割り当てられたすべての qubits がすぐに割り当て解除され、それ以上使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-115">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="e2dcd-116">ターゲットコンピューターでは {0} 、割り当てのために再利用して他のブロックに提供できるように、割り当て解除の直前に qubits が $ \ket $ 状態にあることを想定してい `using` ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-116">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="e2dcd-117">可能な場合は常に、ユニタリ操作を使用して、割り当てられた qubits を $ \ket $ に返し {0} ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-117">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="e2dcd-118">必要に応じて、 @"microsoft.quantum.intrinsic.reset" 操作を使用して qubit を測定し、測定結果を使用して、測定された qubit が $ \ket $ に返されるようにすることができ {0} ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-118">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="e2dcd-119">このような測定値は、残りの qubits を使用してすべての entangを破棄するため、計算に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-119">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="e2dcd-120">借りた Qubits</span><span class="sxs-lookup"><span data-stu-id="e2dcd-120">Borrowed Qubits</span></span>

<span data-ttu-id="e2dcd-121">この `borrowing` ステートメントは、特定の状態にする必要がない、一時的な使用に対して qubits を使用できるようにするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-121">The `borrowing` statement is used to make qubits available for temporary use, which do not need be in a specific state.</span></span>

<span data-ttu-id="e2dcd-122">借用機構を使用すると、計算中にスクラッチ領域として使用できる qubits を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-122">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span>
<span data-ttu-id="e2dcd-123">通常、これらの qubits はクリーンな状態ではありません。つまり、$ \ket $ などの既知の状態で初期化されるとは限りません。 {0}</span><span class="sxs-lookup"><span data-stu-id="e2dcd-123">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="e2dcd-124">これらの状態は不明であるため、クォンタムコンピューターのメモリの他の部分との間でも、これらは "ダーティな" qubits と呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-124">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="e2dcd-125">バインドは、ステートメントと同じパターンおよび規則に従い `using` ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-125">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>
<span data-ttu-id="e2dcd-126">たとえば、オブジェクトに適用された</span><span class="sxs-lookup"><span data-stu-id="e2dcd-126">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="e2dcd-127">借用した qubits は不明な状態であり、ステートメントブロックの最後でスコープ外に出ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-127">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="e2dcd-128">借り手は、貸し出しされたときと同じ状態に qubits を残すことをコミットします。つまり、ステートメントブロックの先頭と末尾の状態は同じであると想定されます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-128">The borrower commits to leaving the qubits in the same state they were in when they were borrowed,  i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="e2dcd-129">特に、この状態は必ずしも古典的な状態ではありません。ほとんどの場合、借りているスコープには測定値を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-129">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="e2dcd-130">Qubits を借りている場合、システムはまず、使用中であるが、ステートメントの本体ではアクセスされていない qubits から要求を入力しようとし `borrowing` ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-130">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="e2dcd-131">このような qubits が不足している場合は、要求を完了するために新しい qubits が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-131">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>


<span data-ttu-id="e2dcd-132">ダーティ qubits の既知のユースケースの中では、incrementers の少数の qubits と実装のみを必要とする、マルチ制御の CNOT ゲートの実装があります。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-132">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="e2dcd-133">次の[例](#borrowing-qubits-example)を参照して Q # での使用例をご覧ください。または、借り qubits を利用するアルゴリズムに対して、 [*2n + 2 Qubits と Toffoli ベースのモジュール乗算 2017 (ベースのモジュール乗算) を使用してファクタリング*](https://arxiv.org/abs/1611.07995)したホワイトペーパーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-133">See the [Borrowing Qubits Example](#borrowing-qubits-example) below to see an example of their use in Q#, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>


## <a name="intrinsic-operations"></a><span data-ttu-id="e2dcd-134">組み込みの操作</span><span class="sxs-lookup"><span data-stu-id="e2dcd-134">Intrinsic Operations</span></span>

<span data-ttu-id="e2dcd-135">割り当てられた後、qubit を関数と操作に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-135">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="e2dcd-136">ある意味では、これは、実行可能なアクションがすべて操作として定義されているため、Q # プログラムが qubit を使用して実行できることです。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-136">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="e2dcd-137">これらの操作については、[組み込みの操作と関数](xref:microsoft.quantum.libraries.standard.prelude)で詳しく説明しますが、ここでは、qubits との対話に使用できるいくつかの便利な操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-137">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="e2dcd-138">1つ目の方法として、1つの $Z $、$Y $、および $ $X、 `X` それぞれが型を持つ組み込みの操作、、およびによって Q # で表され `Y` `Z` `(Qubit => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-138">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="e2dcd-139">「組み込みの[操作と関数](xref:microsoft.quantum.libraries.standard.prelude)」で説明されているように、$X $ として、がビットフリップ演算であるか、そうではないと考えることができ `X` ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-139">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="e2dcd-140">この操作を実行すると、 `X` いくつかのクラシックビット文字列 $s $: で $ \ket{s_0 s_1 \ ドット s_n} $ という形式の状態を準備できます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-140">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="e2dcd-141">後で、手動によるフロー制御を必要としない、この操作を記述するよりコンパクトな方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-141">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="e2dcd-142">また、 {0} {1} {2} {-} {0} {1} {2} 組み込み操作によって Q # で表される \ket transform $H $ を使用して、$ \ket{+} = \ left (\ket + \ket →)/\ sqrt $ および $ \ket = \ left (\ket-Hadamard/right)/\ sqrt $ などの状態を準備することもでき `H : (Qubit => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-142">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="e2dcd-143">測定</span><span class="sxs-lookup"><span data-stu-id="e2dcd-143">Measurements</span></span>

<span data-ttu-id="e2dcd-144">組み込みの非インサム演算である操作を使用する `Measure` と、型のオブジェクトから古典的な情報を抽出し、その結果 `Qubit` として古典的な値を割り当てることができます。これには予約済みの型があり、結果はクォンタム状態ではなくなっていることを `Result` 示します。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-144">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="e2dcd-145">への入力 `Measure` は、Bloch 球の p li 軸で、型 `Pauli` (たとえば、) の値 `PauliX` と型の値で表され `Qubit` ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-145">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="e2dcd-146">単純な例として、次の操作があります。この操作では、$ \ket $ 状態に1つの qubit が割り当てられ、 {0} Hadamard 操作が適用され、その `H` 結果が基になり `PauliZ` ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-146">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="e2dcd-147">次の演算では、より複雑な例が示されています。この操作では、 `true` 型のレジスタ内のすべての qubits が、指定された pare によって測定された場合は、ブール値を返し、それ以外の場合は `Qubit[]` を返し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-147">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

## <a name="borrowing-qubits-example"></a><span data-ttu-id="e2dcd-148">借りた Qubits の例</span><span class="sxs-lookup"><span data-stu-id="e2dcd-148">Borrowing Qubits Example</span></span>

<span data-ttu-id="e2dcd-149">キャノンには、キーワードを使用する例があり `borrowing` ます。たとえば、 `MultiControlledXBorrow` 次に定義されている関数です。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-149">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="e2dcd-150">は、 `controls` 操作に追加する必要があるコントロール qubits を示す場合 `X` 、 `Length(controls)-2` この実装によって多くのダーティ ancillas の全体が追加されます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-150">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="e2dcd-151">結合子は、 `With` adjoint をサポートする操作 (つまり、 `WithA` この例では---されています) に適用される---の形式で広く使用されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-151">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example.</span></span>
<span data-ttu-id="e2dcd-152">これは、 `With` 内部操作にのみ制御を反映する構造体にコントロールを追加するため、適切なプログラミングスタイルです。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-152">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="e2dcd-153">さらに、ここでは、操作のに加えて、操作の本体の実装が明示的に指定されていることに注意してください。これは、ステートメントを再実行することで `body` `controlled` は `controlled auto` ありません。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-153">Further, note that here in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="e2dcd-154">その理由は、の各ゲートにコントロールを追加する場合と比較して、役に立つコントロールをさらに簡単に追加する方法です `body` 。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-154">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="e2dcd-155">このコードを別のキャノン関数と比較して、 `MultiControlledXClean` 乗算制御演算を実装するのと同じ目標を達成し `X` ます。ただし、メカニズムを使用していくつかの clean qubits を使用し `using` ます。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-155">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="whats-next"></a><span data-ttu-id="e2dcd-156">次の課題</span><span class="sxs-lookup"><span data-stu-id="e2dcd-156">What's Next?</span></span>
<span data-ttu-id="e2dcd-157">Q # の[制御フロー](xref:microsoft.quantum.guide.controlflow)について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2dcd-157">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>