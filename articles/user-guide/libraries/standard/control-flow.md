---
title: Q#標準 libararies フロー制御
description: Microsoft 標準ライブラリのフロー制御操作と関数について説明し Q# ます。
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1cfef50cf2bbecd2043972a662edd8120c5570ec
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835623"
---
# <a name="higher-order-control-flow"></a><span data-ttu-id="da844-103">上位制御フロー</span><span class="sxs-lookup"><span data-stu-id="da844-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="da844-104">標準ライブラリの主要な役割の1つは、高レベルのアルゴリズムアイデアを [量子プログラム](https://en.wikipedia.org/wiki/Quantum_programming)として簡単に表現できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="da844-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="da844-105">そのため、 Q# キャノンはさまざまなフロー制御の構成要素を提供しており、それぞれが関数と操作の部分的な適用を使用して実装されています。</span><span class="sxs-lookup"><span data-stu-id="da844-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="da844-106">すぐに例にジャンプする場合は、レジスタに "CNOT はしご" を構築したいケースを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="da844-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="da844-107">繰り返しとループを使用して、このパターンを表現でき `for` ます。</span><span class="sxs-lookup"><span data-stu-id="da844-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="da844-108">ただし、などの <xref:microsoft.quantum.canon.applytoeachca> および配列操作関数で表現 <xref:microsoft.quantum.arrays.zip> されますが、これははるかに短く、読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="da844-108">Expressed in terms of <xref:microsoft.quantum.canon.applytoeachca> and array manipulation functions such as <xref:microsoft.quantum.arrays.zip>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="da844-109">このセクションの残りの部分では、canon to コンパクト express クォンタムプログラムによって提供されるさまざまなフロー制御操作と関数の使用方法について、いくつかの例を提供します。</span><span class="sxs-lookup"><span data-stu-id="da844-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="da844-110">配列と範囲に対する操作と関数の適用</span><span class="sxs-lookup"><span data-stu-id="da844-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="da844-111">キャノンによって提供される主な抽象化の1つは、イテレーションのことです。</span><span class="sxs-lookup"><span data-stu-id="da844-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="da844-112">たとえば、という形式の $U、1つの 1 qubit の $U である $ のような形式のユニタリを使用します。</span><span class="sxs-lookup"><span data-stu-id="da844-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="da844-113">では Q# 、を使用し <xref:microsoft.quantum.arrays.indexrange> て、これをレジスタに対するループとして表すことができ `for` ます。</span><span class="sxs-lookup"><span data-stu-id="da844-113">In Q#, we might use <xref:microsoft.quantum.arrays.indexrange> to represent this as as a `for` loop over a register:</span></span>

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

<span data-ttu-id="da844-114">その後、この新しい操作を使用して、$H/otimes/cドット/otimes `HAll(register)` h $ に適用できます。</span><span class="sxs-lookup"><span data-stu-id="da844-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="da844-115">ただし、特に大きなアルゴリズムでは、これは面倒です。</span><span class="sxs-lookup"><span data-stu-id="da844-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="da844-116">さらに、この方法は、各 qubit に適用する特定の操作に特化しています。</span><span class="sxs-lookup"><span data-stu-id="da844-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="da844-117">このアルゴリズムの概念をより明示的に表現するために、操作がファーストクラスであるという事実を使用できます。</span><span class="sxs-lookup"><span data-stu-id="da844-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="da844-118">ここで、サフィックスは、 `CA` への呼び出し `ApplyToEach` がそれ自体が adjointable で、制御可能であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="da844-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="da844-119">したがって、 `U` で `Adjoint` とがサポートされている場合、 `Controlled` 次の行が同等になります。</span><span class="sxs-lookup"><span data-stu-id="da844-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="da844-120">特に、これは、 `ApplyToEachCA` adjoint の特殊化が自動生成される操作に、の呼び出しが表示される可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="da844-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="da844-121">同様に、 <xref:microsoft.quantum.canon.applytoeachindex> は、フォームのパターンを表すのに便利です。また、は、 `U(0, targets[0]); U(1, targets[1]); ...` 入力でサポートされている機能の組み合わせごとにバージョンを提供します。</span><span class="sxs-lookup"><span data-stu-id="da844-121">Similarly, <xref:microsoft.quantum.canon.applytoeachindex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="da844-122">`ApplyToEach` は、以外の入力を受け取る操作で使用できるように、型指定されたパラメーターです `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="da844-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="da844-123">たとえば、 `codeBlocks` が復旧する必要がある値の配列であるとし <xref:microsoft.quantum.errorcorrection.logicalregister> ます。</span><span class="sxs-lookup"><span data-stu-id="da844-123">For example, suppose that `codeBlocks` is an array of <xref:microsoft.quantum.errorcorrection.logicalregister> values that need to be recovered.</span></span>
> <span data-ttu-id="da844-124">次に `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` 、エラー修正コード `code` と復旧関数 `recoveryFn` を各ブロックに個別に適用します。</span><span class="sxs-lookup"><span data-stu-id="da844-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="da844-125">これは、従来の入力に対しても保持されます。で `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` は、$-pi/$2 の回転が $X $ に対して適用され、$Y $ に関する $pi/$3 の回転が適用されます。</span><span class="sxs-lookup"><span data-stu-id="da844-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="da844-126">また、キャノンでは、 Q# 関数型プログラミングに慣れている古典的な列挙パターンもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="da844-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="da844-127">たとえば、は、 <xref:microsoft.quantum.arrays.fold> リストに対して関数を縮小するために、パターン $f (f (s \_ {\ text{\ text{\ text{\ text{\ text{\ text{\ text{\ text{\ text{\ text{/text{\), \_ \_ \ ドット) $) を実装します。</span><span class="sxs-lookup"><span data-stu-id="da844-127">For instance, <xref:microsoft.quantum.arrays.fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="da844-128">このパターンを使用すると、合計、製品、最小、最大化、およびその他の機能を実装できます。</span><span class="sxs-lookup"><span data-stu-id="da844-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="da844-129">同様に、やなどの関数を <xref:microsoft.quantum.arrays.mapped> 使用して、 <xref:microsoft.quantum.arrays.mappedbyindex> の関数型プログラミングの概念を表現でき Q# ます。</span><span class="sxs-lookup"><span data-stu-id="da844-129">Similarly, functions like <xref:microsoft.quantum.arrays.mapped> and <xref:microsoft.quantum.arrays.mappedbyindex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="da844-130">操作と関数の作成</span><span class="sxs-lookup"><span data-stu-id="da844-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="da844-131">キャノンの take 操作および関数によって提供される制御フローの構造を入力として提供します。これにより、複数の操作または関数を1つの呼び出し可能に構成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="da844-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="da844-132">たとえば、"^ {\ dagger} $ $UVU パターンは、 <xref:microsoft.quantum.canon.applywith> このパターンの抽象化として、キャノンが操作を提供するクォンタムプログラミングで非常に一般的です。</span><span class="sxs-lookup"><span data-stu-id="da844-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:microsoft.quantum.canon.applywith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="da844-133">この抽象化を使用すると、 `Controlled` シーケンスに対して動作 `U(qubit); V(qubit); Adjoint U(qubit);` する必要がないので、回線への compliation をより効率的に行うことができ `U` ます。</span><span class="sxs-lookup"><span data-stu-id="da844-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="da844-134">これを確認するには、$c (U) $ を表す、 `Controlled U([control], target)` $c (V) $ を同じ方法で定義します。</span><span class="sxs-lookup"><span data-stu-id="da844-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="da844-135">次に、任意の状態を $ \ket{\psi} $ にします。 \begin{align} c (U) c (V) c (U) ^ \ ダガー \ket/ {1} otimes \ket{\psi} & = \ket/ {1} otimes (uvu ^ {-dagger} \ket{\psi}) \\ \\ & = (\ bold 完了 \ otimes u) (c (V)) (\ bold Done/otimes u ^ ダガー) \ket/ {1} otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="da844-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="da844-136">の定義によって \end{align} `Controlled` ます。</span><span class="sxs-lookup"><span data-stu-id="da844-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="da844-137">一方、\begin{align} c (U) c (V) c (U) ^ \ ダガー \ket/ {0} otimes \ket{\psi} & = \ket/otimes {0} \ket{\psi} \\ \\ & = \ket/ {0} otimes (UU ^ \ ダガー \ket{\psi}) \\ \\ & = (\ bold done/Otimes u) (c (V)) (\ bold done/otimes u ^) \ket、 {0} otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="da844-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="da844-138">\end{align} によって、すべての入力状態に $U $ out をこの方法で考慮することができます。</span><span class="sxs-lookup"><span data-stu-id="da844-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="da844-139">つまり、$c (UVU ^ \ ダガー) = U c (V) U ^ \ ダガー $ です。</span><span class="sxs-lookup"><span data-stu-id="da844-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="da844-140">操作の制御は一般にコストがかかる場合があるため、やなどの制御されたバリアントを使用する `WithC` と、 `WithCA` 適用する必要があるコントロールの数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="da844-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="da844-141">$U $ をファクタリングするもう1つの結果は、ファンクタをに適用する方法さえわからないことです `Controlled` `U` 。</span><span class="sxs-lookup"><span data-stu-id="da844-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="da844-142">`ApplyWithCA` したがって、想定されるほど弱いシグネチャがあります。</span><span class="sxs-lookup"><span data-stu-id="da844-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="da844-143">同様に、は、 <xref:microsoft.quantum.canon.bound> 他の一連の操作を順番に適用する操作を生成します。</span><span class="sxs-lookup"><span data-stu-id="da844-143">Similarly, <xref:microsoft.quantum.canon.bound> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="da844-144">たとえば、次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="da844-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

<span data-ttu-id="da844-145">反復パターンと組み合わせることで、これは特に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="da844-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="da844-146">時間順序の構成</span><span class="sxs-lookup"><span data-stu-id="da844-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="da844-147">それでも、部分的なアプリケーションや従来の関数の観点からフロー制御を検討し、従来のフロー制御の観点からは、非常に高度なクォンタムの概念をモデル化することができます。</span><span class="sxs-lookup"><span data-stu-id="da844-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="da844-148">このような類似性は、順序付け演算子が呼び出し操作の副作用と完全に対応していることを認識することによって正確になります。これは、他のすべての入力演算子の観点からの特定の呼び出しシーケンスを作成して、特定の順番演算子として動作するための命令を出力する従来のサブルーチンの呼び出しシーケンスを作成する</span><span class="sxs-lookup"><span data-stu-id="da844-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="da844-149">このビューでは、はマトリックス製品を正確に表したものです。これは、 `Bound` `Bound([A, B])(target)` がと等価であり、 `A(target); B(target);` さらに、$BA $ に対応する呼び出しシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="da844-149">Under this view, `Bound` is precisely the representation of the matrix product, since `Bound([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="da844-150">より高度な例として、 [Trotter – Suzuki の拡張](https://arxiv.org/abs/math-ph/0506007v1)があります。</span><span class="sxs-lookup"><span data-stu-id="da844-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="da844-151">[データ構造](xref:microsoft.quantum.libraries.data-structures)の Dynamical Generator 表現に関するセクションで説明したように、Trotter – Suzuki 拡張は、マトリックス指数を表現するために特に便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="da844-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="da844-152">たとえば、最小の順序で展開を適用すると、$ および $B $ $A の演算子に対して、$A = A ^ \ ダガー $ と $B = B ^ \ ダガー $ のようになります。 \begin{align} \ tag{★} \ label{eq: trotter-suzuki-0} \ exp (i [A + B] t) = \ lim_ {n}/left (\ exp (i A t/n) \ exp (i B t/n)) ^ n</span><span class="sxs-lookup"><span data-stu-id="da844-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="da844-153">\end{align} 表現では、$A + B $ の下にある状態を、$A $ と $B $ アロンの順に進化させることで、ほぼ進化できることがわかります。</span><span class="sxs-lookup"><span data-stu-id="da844-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="da844-154">$A $ の下で、 `A : (Double, Qubit[]) => Unit` ^ {i t A} $ $e 適用される操作によって進化が示されている場合は、呼び出しシーケンスの再配置に関して Trotter – Suzuki 拡張の表現が明確になります。</span><span class="sxs-lookup"><span data-stu-id="da844-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="da844-155">具体的には、となどの操作を指定した場合、 `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` `A = U(0, _, _)` `B = U(1, _, _)` `U` フォームのシーケンスを生成することにより、time $t $ の整数を表す新しい操作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="da844-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="da844-156">この時点で、Trotter – Suzuki 拡張については、 *クォンタムメカニズムをまったく参照する*必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="da844-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="da844-157">拡張は、実質的には $ \eqref{eq: trotter-0} $ によって実現される非常に具体的な反復パターンです。</span><span class="sxs-lookup"><span data-stu-id="da844-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="da844-158">この反復パターンは、次の方法で実装され <xref:microsoft.quantum.canon.decomposeintotimestepsca> ます。</span><span class="sxs-lookup"><span data-stu-id="da844-158">This iteration pattern is implemented by <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="da844-159">のシグネチャは `DecomposeIntoTimeStepsCA` 、の一般的なパターンに従います Q# 。ここでは、配列またはその場で計算される要素を使用してサポートされるコレクションは、最初の要素が長さを示す値である組によって表され `Int` ます。</span><span class="sxs-lookup"><span data-stu-id="da844-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="da844-160">まとめ: 操作の制御</span><span class="sxs-lookup"><span data-stu-id="da844-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="da844-161">最後に、キャノンは、 `Controlled` クォンタム操作の条件を追加する方法を提供することで、ファンクタ上に構築されます。</span><span class="sxs-lookup"><span data-stu-id="da844-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="da844-162">特に、クォンタムの算術演算では、$ \ket{0\cdots 0} $ 以外の計算ベースの状態に対する条件演算に共通です。</span><span class="sxs-lookup"><span data-stu-id="da844-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="da844-163">上記の制御操作と関数を使用すると、1つのステートメントでより一般的なクォンタム条件を実行できます。</span><span class="sxs-lookup"><span data-stu-id="da844-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="da844-164">で <xref:microsoft.quantum.canon.controlledonbitstring> は、そのしくみ (san の種類のパラメーター) に移動して、1つずつ分割します。</span><span class="sxs-lookup"><span data-stu-id="da844-164">Let's jump in to how <xref:microsoft.quantum.canon.controlledonbitstring> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="da844-165">最初に行う必要があるのは、任意の計算基準の状態に対してコントロールを実装する操作を実際に実行する操作を定義することです。</span><span class="sxs-lookup"><span data-stu-id="da844-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="da844-166">ただし、この操作を直接呼び出すのではなく、 `_` 名前の先頭にを追加して、他の場所にある別の構造体の実装であることを示します。</span><span class="sxs-lookup"><span data-stu-id="da844-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

<span data-ttu-id="da844-167">`Bool`指定した操作に適用するエアコンを指定するために使用する、配列として表現されたビットの文字列を使用し `oracle` ます。</span><span class="sxs-lookup"><span data-stu-id="da844-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="da844-168">この操作では実際にアプリケーションが直接実行されるため、コントロールとターゲットレジスタを両方とも使用する必要があり `Qubit[]` ます。</span><span class="sxs-lookup"><span data-stu-id="da844-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="da844-169">次に、 \_ $ \ket{\vec{s}} $ を $ \ket{0\cdots 0} $ に変換することによって、計算基準の状態が $ \ket{\vec{s}} = \ket{s 0 s \_ 1 \ ドット s \_ {n-1}} $ に対する制御が実現することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="da844-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="da844-170">具体的には、$ \ket{\vec{s}} = X ^ {s \_ 0} \ Otimes x ^ {s \_ 1} \ otimes/cドット/otimes x ^ {s \_ {n-1}} \ket{0\cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="da844-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="da844-171">$X ^ {\ dagger} = X $ であるため、これは $ \ket{0\dots 0} = X ^ {s \_ 0}-Otimes x ^ {s 1} \ otimes/ \_ cドット/Otimes x ^ {s \_ {n-1}} \ket{\vec{s}} $ であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="da844-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="da844-172">これにより、$P = X ^ {s \_ 0} \ Otimes x ^ {s \_ 1}/otimes/cドット/otimes x ^ {s \_ {n-1}} $ を適用し、$- `Controlled oracle` vec{s} $ に変換して戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="da844-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="da844-173">この構築は正確 `ApplyWith` であるため、新しい操作の本文をそれに応じて記述します。</span><span class="sxs-lookup"><span data-stu-id="da844-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="da844-174">ここでは、 <xref:microsoft.quantum.canon.applypaulifrombitstring> で使用するために、$P $ を適用し、そのターゲットに部分的に適用してい `ApplyWith` ます。</span><span class="sxs-lookup"><span data-stu-id="da844-174">Here, we have used <xref:microsoft.quantum.canon.applypaulifrombitstring> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="da844-175">ただし、*コントロール*レジスタを目的の形式に変換する必要があることに注意してください。したがって、内部操作はターゲットに部分的に適用され `(Controlled oracle)` ます。 *target*</span><span class="sxs-lookup"><span data-stu-id="da844-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="da844-176">これ `ApplyWith` により、必要に応じて、コントロールレジスタが $P $ に角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="da844-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="da844-177">この時点では、これで完了ですが、新しい操作では、ファンクタを適用するような "感覚" にならないということがわかりません `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="da844-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="da844-178">このため、oracle を制御し、新しい操作を返す関数を記述することによって、新しい制御フローの概念を定義します。</span><span class="sxs-lookup"><span data-stu-id="da844-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="da844-179">このように、新しい関数は、 `Controlled` とキャノンを使用して強力な新しい制御フローコンストラクトを簡単に定義できることを示してい Q# ます。</span><span class="sxs-lookup"><span data-stu-id="da844-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
