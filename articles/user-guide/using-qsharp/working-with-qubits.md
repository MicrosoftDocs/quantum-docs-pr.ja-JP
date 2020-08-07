---
title: 量子ビットの操作
description: 説明の入力
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6808a852ee0de7d3a38ea44e9637eeaa6bea382a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867864"
---
# <a name="working-with-qubits"></a><span data-ttu-id="4c696-103">量子ビットの操作</span><span class="sxs-lookup"><span data-stu-id="4c696-103">Working with qubits</span></span>

<span data-ttu-id="4c696-104">Qubits は、クォンタムコンピューティングにおける情報の基本的なオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="4c696-104">Qubits are the fundamental object of information in quantum computing.</span></span> <span data-ttu-id="4c696-105">Qubits の概要については、「[クォンタムコンピューティングについ](xref:microsoft.quantum.overview.understanding)て」を参照してください。また、数学表現の詳細については、「 [qubits](xref:microsoft.quantum.concepts.qubit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c696-105">For a general introduction to qubits, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), and to dive deeper into their mathematical representation, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span> 

<span data-ttu-id="4c696-106">この記事では、プログラムで qubits を使用して操作する方法について説明し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-106">This article explores how to use and work with qubits in a Q# program.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="4c696-107">この記事で説明されているどのステートメントも、関数の本体内では有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="4c696-107">None of the statements discussed in this article are valid within the body of a function.</span></span> <span data-ttu-id="4c696-108">これらは、操作内でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="4c696-108">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="4c696-109">割り当て (Qubits を)</span><span class="sxs-lookup"><span data-stu-id="4c696-109">Allocating Qubits</span></span>

<span data-ttu-id="4c696-110">物理 qubits は、quantum コンピューターの貴重なリソースであるため、コンパイラのジョブの一部として、それらが可能な限り効率的に使用されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c696-110">Because physical qubits are a precious resource in a quantum computer, part of the compiler's job is to make sure they are being used as efficiently as possible.</span></span>
<span data-ttu-id="4c696-111">そのため、 Q# 特定のステートメントブロック内で使用するには、qubits を*割り当てる*必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c696-111">As such, you need to tell Q# to *allocate* qubits for use within a particular statement block.</span></span>
<span data-ttu-id="4c696-112">Qubits を1つの qubits として割り当てることも、*レジスタ*と呼ばれる qubits の配列として割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="4c696-112">You can allocate qubits as a single qubit, or as an array of qubits, known as a *register*.</span></span> 

### <a name="clean-qubits"></a><span data-ttu-id="4c696-113">Clean qubits</span><span class="sxs-lookup"><span data-stu-id="4c696-113">Clean qubits</span></span>

<span data-ttu-id="4c696-114">ステートメントを使用して、 `using` ステートメントブロック中に使用する新しい qubits を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4c696-114">Use the `using` statement to allocate new qubits for use during a statement block.</span></span>

<span data-ttu-id="4c696-115">ステートメントは、キーワードと、 `using` その後にかっこで囲まれたバインディング `( )` と、qubits が使用可能なステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="4c696-115">The statement consists of the keyword `using`, followed by a binding enclosed in parentheses `( )` and the statement block within which the qubits are available.</span></span>
<span data-ttu-id="4c696-116">バインディングは、ステートメントと同じパターンに従い `let` ます。1つの記号または記号の組、等号 (= `=` )、1つの値、または*初期化子*の一致するタプルのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="4c696-116">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="4c696-117">初期化子は、として指定された1つの qubit、 `Qubit()` または qubit の配列 (は式) に対して使用でき `Qubit[n]` `n` `Int` ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-117">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="4c696-118">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4c696-118">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="4c696-119">この方法で割り当てられた qubits は、$ \ket {0} $ 状態から開始されます。</span><span class="sxs-lookup"><span data-stu-id="4c696-119">Any qubits allocated in this way start off in the $\ket{0}$ state.</span></span> <span data-ttu-id="4c696-120">したがって、前の例で `auxiliary` は、は、状態が $ \ket $ である1つの qubit で、 {0} `register` 5 つの qubit 状態は $ \ket {00000} = \ket/ {0} otimes \ket/ {0} otimes/cドット/otimes \ket {0} $ です。</span><span class="sxs-lookup"><span data-stu-id="4c696-120">Thus in the previous example, `auxiliary` is a single qubit in the state $\ket{0}$, and `register` is in the five-qubit state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="4c696-121">ブロックの末尾に `using` は、そのブロックによって割り当てられたすべての qubits がすぐに割り当て解除され、それ以上使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4c696-121">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="4c696-122">ターゲットコンピューターは、割り当て解除された qubits を再利用し、割り当てのために他のブロックに提供でき `using` ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-122">Target machines can reuse deallocated qubits and offer them to other `using` blocks for allocation.</span></span> <span data-ttu-id="4c696-123">そのため、ターゲットコンピューターでは、割り当て解除の直前に、qubits が $ \ket $ 状態にあることを想定してい {0} ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-123">As such, the target machine expects that qubits are in the $\ket{0}$ state immediately before deallocation.</span></span>
> <span data-ttu-id="4c696-124">可能な場合は常に、ユニタリ操作を使用して、割り当てられた qubits を $ \ket $ に返し {0} ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-124">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="4c696-125">必要に応じて、操作を使用できます @"microsoft.quantum.intrinsic.reset" 。この操作では、演算子を {0} 測定し、結果に基づいて条件付きで演算を実行することで、qubit を $ \ket $ に返します。</span><span class="sxs-lookup"><span data-stu-id="4c696-125">If need be, you can use the @"microsoft.quantum.intrinsic.reset" operation, which returns the qubit to $\ket{0}$ by measuring it and conditionally performing an operation based on the result.</span></span> <span data-ttu-id="4c696-126">このような測定値は、残りの qubits を使用して結び付き破棄し、計算に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4c696-126">Such a measurement destroys any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="4c696-127">借りた Qubits</span><span class="sxs-lookup"><span data-stu-id="4c696-127">Borrowed Qubits</span></span>

<span data-ttu-id="4c696-128">ステートメントを使用して `borrowing` 、一時的な使用のために qubits を割り当てます。これは、特定の状態である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4c696-128">Use the `borrowing` statement to allocate qubits for temporary use, which do not need to be in a specific state.</span></span>

<span data-ttu-id="4c696-129">計算時には、借りた qubits をスクラッチ領域として使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c696-129">You can use borrowed qubits as scratch space during a computation.</span></span>
<span data-ttu-id="4c696-130">これらの qubits は、一般にクリーンな状態ではありません。つまり、$ \ket $ などの既知の状態で初期化されるとは限りません {0} 。</span><span class="sxs-lookup"><span data-stu-id="4c696-130">These qubits are generally not in a clean state, that is, they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="4c696-131">これらの状態は不明であるため、クォンタムコンピューターのメモリの他の部分との間でも、これらは "ダーティな" qubits と呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="4c696-131">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="4c696-132">バインディングは、ステートメントと同じパターンおよび規則に従い `using` ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-132">The binding follows the same pattern and rules as the `using` statement.</span></span>
<span data-ttu-id="4c696-133">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4c696-133">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="4c696-134">借用した qubits は不明な状態であり、ステートメントブロックの最後でスコープ外に出ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-134">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="4c696-135">借り手は、借用したときと同じ状態で qubits を離れるようにコミットします。つまり、ステートメントブロックの先頭と末尾の状態は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c696-135">The borrower commits to leaving the qubits in the same state they were in when they borrowed them; that is, their state at the beginning and the end of the statement block should be the same.</span></span>
<span data-ttu-id="4c696-136">この状態は必ずしも従来の状態ではないため、ほとんどの場合、スコープには測定値を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="4c696-136">Because this state is not necessarily a classical state, in most cases borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="4c696-137">Qubits を借りている場合、システムはまず、使用中であるが、ステートメントの本体ではアクセスされていない qubits から要求を入力しようとし `borrowing` ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-137">When borrowing qubits, the system first tries to fill the request from qubits that are in use but not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="4c696-138">このような qubits が不足している場合は、新しい qubits を割り当てて要求を完了します。</span><span class="sxs-lookup"><span data-stu-id="4c696-138">If there aren't enough such qubits, then it allocates new qubits to complete the request.</span></span>

<span data-ttu-id="4c696-139">ダーティ qubits の既知のユースケースの中では、incrementers の少数の qubits と実装のみを必要とする、マルチ制御の CNOT ゲートの実装があります。</span><span class="sxs-lookup"><span data-stu-id="4c696-139">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="4c696-140">での使用例につい Q# ては、この記事の「[貸し出し Qubits の例](#borrowing-qubits-example)」を参照するか、 [*2n + 2 qubits と Toffoli ベースのモジュール乗算 (Based*](https://arxiv.org/abs/1611.07995) 、roetteler、および svore 2017) を使用して、借り qubits を利用するアルゴリズムを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4c696-140">For an example of their use in Q#, see [Borrowing Qubits Example](#borrowing-qubits-example) in this article, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="4c696-141">組み込みの操作</span><span class="sxs-lookup"><span data-stu-id="4c696-141">Intrinsic Operations</span></span>

<span data-ttu-id="4c696-142">割り当てられると、関数と操作に qubit を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="4c696-142">Once allocated, you can pass a qubit to functions and operations.</span></span>
<span data-ttu-id="4c696-143">これは、 Q# 実行可能なアクションがすべて操作として定義されているため、プログラムが qubit を使用して実行できることです。</span><span class="sxs-lookup"><span data-stu-id="4c696-143">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>

<span data-ttu-id="4c696-144">この記事では、 Q# qubits との対話に使用できるいくつかの便利な操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c696-144">This article discusses a few useful Q# operations that you can use to interact with qubits.</span></span>
<span data-ttu-id="4c696-145">これらおよび他の詳細については、「[組み込みの操作と関数](xref:microsoft.quantum.libraries.standard.prelude)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c696-145">For more detail about these and others, see [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span> 

<span data-ttu-id="4c696-146">1つ目の方法として、単 qubit の Pare Li 演算子 $X $、$Y $、および $Z $ は、 Q# [`X`](xref:microsoft.quantum.intrinsic.x) それぞれが型を持つ組み込みの操作である、、およびによって表され [`Y`](xref:microsoft.quantum.intrinsic.y) [`Z`](xref:microsoft.quantum.intrinsic.z) `(Qubit => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-146">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations [`X`](xref:microsoft.quantum.intrinsic.x), [`Y`](xref:microsoft.quantum.intrinsic.y), and [`Z`](xref:microsoft.quantum.intrinsic.z), each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="4c696-147">「組み込みの[操作と関数](xref:microsoft.quantum.libraries.standard.prelude)」で説明されているように、$ $X `X` は、ビットフリップ演算または NOT gate として考えられます。</span><span class="sxs-lookup"><span data-stu-id="4c696-147">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="4c696-148">操作を使用して、 `X` $ \ket{s_0 s_1 \ ドット s_n} $ の形式の状態を準備できます。これは、一部のクラシックビット文字列 $s $:</span><span class="sxs-lookup"><span data-stu-id="4c696-148">You can use the `X` operation to prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="4c696-149">後で、手動による制御フローを必要としない、この操作をよりコンパクトな方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="4c696-149">Later, you will see more compact ways of writing this operation that do not require manual control flow.</span></span>

<span data-ttu-id="4c696-150">組み込み操作によって表される \Ket transform $H $ を使用して、$ \ket{+} = \ left (\ket {0} + \ket {1} /right)/\ sqrt {2} $ and $ \ket = (\ket-Hadamard/right)/-sqrt $ などの状態を準備することもでき {-} {0} {1} {2} Q# [`H`](xref:microsoft.quantum.intrinsic.h) ます (型 (qubit => Unit is 形容詞 + Ctl) ')。</span><span class="sxs-lookup"><span data-stu-id="4c696-150">You can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation [`H`](xref:microsoft.quantum.intrinsic.h) (also of type (Qubit => Unit is Adj + Ctl)\`):</span></span>

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

## <a name="measurements"></a><span data-ttu-id="4c696-151">測定</span><span class="sxs-lookup"><span data-stu-id="4c696-151">Measurements</span></span>

<span data-ttu-id="4c696-152">個々の qubits の測定は、 [Bloch 球の p](xref:microsoft.quantum.glossary#bloch-sphere)li 軸によって表される異なるベースで実行できます。</span><span class="sxs-lookup"><span data-stu-id="4c696-152">Measurements of individual qubits can be performed in different bases, each represented by a Pauli axis on the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere).</span></span>
<span data-ttu-id="4c696-153">*計算基準*はベースを指し、 `PauliZ` 測定に最も一般的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4c696-153">The *computational basis* refers to the `PauliZ` basis, and is the most common basis used for measurement.</span></span>

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a><span data-ttu-id="4c696-154">1つの qubit を基準にして測定する `PauliZ`</span><span class="sxs-lookup"><span data-stu-id="4c696-154">Measure a single qubit in the `PauliZ` basis</span></span>

<span data-ttu-id="4c696-155">演算を使用します [`M`](xref:microsoft.quantum.intrinsic.m) 。この操作は組み込みの非イン数値演算であり、1つの qubit を `PauliZ` 基準にして、その結果に古典的な値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4c696-155">Use the [`M`](xref:microsoft.quantum.intrinsic.m) operation, which is a built-in intrinsic non-unitary operation, to measure a single qubit in the `PauliZ` basis and assign a classical value to the result.</span></span>
<span data-ttu-id="4c696-156">`M`には、予約された戻り値の型があります `Result` 。これは、値を取得するか、測定された `Zero` `One` 状態 $ \ket {0} $ または $ \ket $-に対応します。これは、 {1} 結果がクォンタムの状態ではなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="4c696-156">`M` has a reserved return type, `Result`, which can only take values `Zero` or `One` corresponding to the measured states $\ket{0}$ or $\ket{1}$ - indicating that the result is no longer a quantum state.</span></span>

<span data-ttu-id="4c696-157">単純な例として、次の操作があります。この操作では、$ \ket $ 状態に1つの qubit が割り当てられ、 {0} Hadamard 操作が適用され、その `H` 結果が基になり `PauliZ` ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-157">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

### <a name="measure-one-or-more-qubits-in-specific-bases"></a><span data-ttu-id="4c696-158">特定のベースの1つ以上の qubits を測定する</span><span class="sxs-lookup"><span data-stu-id="4c696-158">Measure one or more qubits in specific bases</span></span>

<span data-ttu-id="4c696-159">特定のベースの1つ以上の qubits の配列を測定するには、操作を使用し [`Measure`](xref:microsoft.quantum.intrinsic.measure) ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-159">To measure an array of one or more qubits in specific bases, you can use the [`Measure`](xref:microsoft.quantum.intrinsic.measure) operation.</span></span>

<span data-ttu-id="4c696-160">への入力 `Measure` は `Pauli` 、型 (たとえば、) の配列で `[PauliX, PauliZ, PauliZ]` あり、qubits の配列です。</span><span class="sxs-lookup"><span data-stu-id="4c696-160">The inputs to `Measure` are an array of `Pauli` types (for example, `[PauliX, PauliZ, PauliZ]`) and an array of qubits.</span></span>

<span data-ttu-id="4c696-161">次の演算では、より複雑な例が示されています。この操作では、 `true` 型のレジスタ内のすべての qubits が、指定された pare によって測定された場合は、ブール値を返し、それ以外の場合は `Qubit[]` を返し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-161">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="4c696-162">この例では、一度 `Measure` に1つずつ個別の qubits に対してのみが実行されることに注意してくださいが、この操作は複数の qubits の結合測定に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="4c696-162">Note that this example still only performs `Measure` on individual qubits one at a time, but the operation can be extended to joint measurements on multiple qubits.</span></span>

## <a name="borrowing-qubits-example"></a><span data-ttu-id="4c696-163">借りた Qubits の例</span><span class="sxs-lookup"><span data-stu-id="4c696-163">Borrowing Qubits Example</span></span>

<span data-ttu-id="4c696-164">次の関数のように、キーワードを使用するキャノンの例があり `borrowing` `MultiControlledXBorrow` ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-164">There are examples in the canon that use the `borrowing` keyword, such as the following function `MultiControlledXBorrow`.</span></span> <span data-ttu-id="4c696-165">が `controls` 操作に追加する制御 qubits を `X` 示す場合、この実装によって追加されるダーティ[ancillas](xref:microsoft.quantum.glossary#ancilla)の数はに `Length(controls)-2` なります。</span><span class="sxs-lookup"><span data-stu-id="4c696-165">If `controls` denotes the control qubits to add to an `X` operation, then the number of dirty [ancillas](xref:microsoft.quantum.glossary#ancilla) added by this implementation is `Length(controls)-2`.</span></span>

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

<span data-ttu-id="4c696-166">この例では、連結子の広範な使用を、 `With` adjoint をサポートする操作 (など) に適用できる形式で使用して `WithA` います。</span><span class="sxs-lookup"><span data-stu-id="4c696-166">Note that this example used extensive use of the `With` combinator, in its form that is applicable for operations that support adjoint, for example, `WithA`.</span></span>
<span data-ttu-id="4c696-167">これは、 `With` 内部操作にのみ制御を反映する構造体にコントロールを追加するため、適切なプログラミングスタイルです。</span><span class="sxs-lookup"><span data-stu-id="4c696-167">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="4c696-168">また、操作のに加えて、操作の本体の実装が明示的に指定されていることにも注意してください。これは、 `body` `controlled` ステートメントを実行するのでは `controlled auto` ありません。</span><span class="sxs-lookup"><span data-stu-id="4c696-168">Also note that, in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="4c696-169">その理由は、回線の構造により、コントロールをさらに追加するのは簡単です。これは、内の各ゲートにコントロールを追加する場合と比べて便利です `body` 。</span><span class="sxs-lookup"><span data-stu-id="4c696-169">The reason for this is that, because of the structure of the circuit, it is easy to add further controls, which is beneficial compared to adding control to each gate in the `body`.</span></span> 

<span data-ttu-id="4c696-170">このコードを別のキャノン関数と比較して、 `MultiControlledXClean` 乗算制御演算を実装するのと同じ目標を達成し `X` ます。ただし、メカニズムを使用していくつかの clean qubits を使用し `using` ます。</span><span class="sxs-lookup"><span data-stu-id="4c696-170">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="4c696-171">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4c696-171">Next steps</span></span>

<span data-ttu-id="4c696-172">の[制御フロー](xref:microsoft.quantum.guide.controlflow)について説明 Q# します。</span><span class="sxs-lookup"><span data-stu-id="4c696-172">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>