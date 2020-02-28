---
title: 'Q # 標準ライブラリのデータ構造'
description: 'Microsoft Q # 標準ライブラリのデータ構造、oracles、dynamical ジェネレーターについて説明します。'
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 46ac6794d1e21e111aa1d98e11a6f83194f8d54e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907785"
---
# <a name="data-structures-and-modeling"></a><span data-ttu-id="899f1-103">データ構造とモデリング</span><span class="sxs-lookup"><span data-stu-id="899f1-103">Data Structures and Modeling</span></span> #

## <a name="classical-data-structures"></a><span data-ttu-id="899f1-104">典型的データ構造</span><span class="sxs-lookup"><span data-stu-id="899f1-104">Classical Data Structures</span></span> ##

<span data-ttu-id="899f1-105">また、ユーザー定義型を使用して、クォンタムの概念を表します。また、キャノンシステムの制御に使用される典型的なデータを操作するための操作、関数、および型も提供します。</span><span class="sxs-lookup"><span data-stu-id="899f1-105">Along with user-defined types for representing quantum concepts, the canon also provides operations, functions, and types for working with classical data used in the control of quantum systems.</span></span>
<span data-ttu-id="899f1-106">たとえば、<xref:microsoft.quantum.arrays.reversed> 関数は、配列を入力として受け取り、同じ配列を逆の順序で返します。</span><span class="sxs-lookup"><span data-stu-id="899f1-106">For instance, the <xref:microsoft.quantum.arrays.reversed> function takes an array as input and returns the same array in reverse order.</span></span>
<span data-ttu-id="899f1-107">これは `Qubit[]` 型の配列に対して使用できます。これにより、整数のクォンタム表現間で変換を行うときに、不要な $/演算子名 {swap} $ ゲートが適用されるのを回避できます。</span><span class="sxs-lookup"><span data-stu-id="899f1-107">This can then be used on an array of type `Qubit[]` to avoid having to apply unnecessary $\operatorname{SWAP}$ gates when converting between quantum representations of integers.</span></span>
<span data-ttu-id="899f1-108">同様に、前のセクションでは、ランダムアクセスコレクションを表すために `(Int, Int -> T)` フォームの種類を示しています。そのため、<xref:microsoft.quantum.arrays.lookupfunction> 関数は、配列型からこのような型を構築する便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="899f1-108">Similarly, we saw in the previous section that types of the form `(Int, Int -> T)` can be useful for representing random access collections, so the <xref:microsoft.quantum.arrays.lookupfunction> function provides a convenient way of constructing such types from array types.</span></span>

### <a name="pairs"></a><span data-ttu-id="899f1-109">座標</span><span class="sxs-lookup"><span data-stu-id="899f1-109">Pairs</span></span> ###

<span data-ttu-id="899f1-110">キャノンは、分解によるタプルへのアクセスを補完する、ペアに対する関数形式の表記をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="899f1-110">The canon supports functional-style notation for pairs, complementing accessing tuples by deconstruction:</span></span>

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a><span data-ttu-id="899f1-111">配列</span><span class="sxs-lookup"><span data-stu-id="899f1-111">Arrays</span></span> ###

<span data-ttu-id="899f1-112">Canon には、配列を操作するための関数がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="899f1-112">The canon provides several functions for manipulating arrays.</span></span>
<span data-ttu-id="899f1-113">これらの関数は型パラメーター化されるため、任意の Q # 型の配列と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="899f1-113">These functions are type-parameterized, and thus can be used with arrays of any Q# type.</span></span>
<span data-ttu-id="899f1-114">たとえば、<xref:microsoft.quantum.arrays.reversed> 関数は、入力とは逆の順序で要素を持つ新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="899f1-114">For instance, the <xref:microsoft.quantum.arrays.reversed> function returns a new array whose elements are in reverse order from its input.</span></span>
<span data-ttu-id="899f1-115">これは、操作を呼び出すときに、クォンタムレジスタがどのように表されるかを変更するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="899f1-115">This can be used to change how a quantum register is represented when calling operations:</span></span>

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

<span data-ttu-id="899f1-116">同様に、<xref:microsoft.quantum.arrays.subarray> 関数は、配列の要素の順序を変更したり、サブセットを取得したりするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="899f1-116">Similarly, the <xref:microsoft.quantum.arrays.subarray> function can be used to reorder or take subsets of the elements of an array:</span></span>

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

<span data-ttu-id="899f1-117">フロー制御と組み合わせると、<xref:microsoft.quantum.arrays.zip> などの配列操作関数は、クォンタムプログラムを表す強力な方法を提供できます。</span><span class="sxs-lookup"><span data-stu-id="899f1-117">When combined with flow control, array manipulation functions such as <xref:microsoft.quantum.arrays.zip> can provide a powerful way to express quantum programs:</span></span>

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zip([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a><span data-ttu-id="899f1-118">Oracles</span><span class="sxs-lookup"><span data-stu-id="899f1-118">Oracles</span></span> ##

<span data-ttu-id="899f1-119">フェーズの[推定](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm)と[振幅増幅](https://en.wikipedia.org/wiki/Amplitude_amplification)の資料では、oracle の概念が頻繁に表示されます。</span><span class="sxs-lookup"><span data-stu-id="899f1-119">In the [phase estimation](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) and [amplitude amplification](https://en.wikipedia.org/wiki/Amplitude_amplification) literature the concept of an oracle appears frequently.</span></span>
<span data-ttu-id="899f1-120">ここで、oracle という用語は、qubits のセットに対して動作し、その回答をフェーズとして返すブラックボックスクォンタムサブルーチンを指します。</span><span class="sxs-lookup"><span data-stu-id="899f1-120">Here the term oracle refers to a blackbox quantum subroutine that acts upon a set of qubits and returns the answer as a phase.</span></span>
<span data-ttu-id="899f1-121">多くの場合、このサブルーチンは、他のいくつかのパラメーターに加えて oracle を受け入れるクォンタムアルゴリズムへの入力と考えることができます。また、一連のクォンタム操作を適用し、このクォンタムサブルーチンの呼び出しを基本的なゲートと同様に処理します。</span><span class="sxs-lookup"><span data-stu-id="899f1-121">This subroutine often can be thought of as an input to a quantum algorithm that accepts the oracle, in addition to some other parameters, and applies a series of quantum operations and treating a call to this quantum subroutine as if it were a fundamental gate.</span></span>
<span data-ttu-id="899f1-122">当然ながら、より大きなアルゴリズムを実際に実装するためには、oracle の根本的な分解を基本的なゲートに提供する必要がありますが、このような分解は、oracle を呼び出すアルゴリズムを理解するためには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="899f1-122">Obviously, in order to actually implement the larger algorithm a concrete decomposition of the oracle into fundamental gates must be provided but such a decomposition is not needed in order to understand the algorithm that calls the oracle.</span></span>
<span data-ttu-id="899f1-123">Q # では、この抽象化は、操作がファーストクラスの値であることによって表されます。これにより、操作を、ブラックボックス方式でクォンタムアルゴリズムの実装に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="899f1-123">In Q#, this abstraction is represented by using that operations are first-class values, such that operations can be passed to implementations of quantum algorithms in a black-box manner.</span></span>
<span data-ttu-id="899f1-124">さらに、ユーザー定義型を使用して、さまざまな oracle 表現をタイプセーフな方法でラベル付けすることで、さまざまな種類のブラックボックス操作を誤って混同ことが困難になります。</span><span class="sxs-lookup"><span data-stu-id="899f1-124">Moreover, user-defined types are used to label the different oracle representations in a type-safe way, making it difficult to accidentally conflate different kinds of black box operations.</span></span>

<span data-ttu-id="899f1-125">このような oracles は、 [Grover の検索](https://en.wikipedia.org/wiki/Grover%27s_algorithm)やクォンタムシミュレーションアルゴリズムなどの有名な例を含む、さまざまなコンテキストで表示されます。</span><span class="sxs-lookup"><span data-stu-id="899f1-125">Such oracles appear in a number of different contexts, including famous examples such as [Grover's search](https://en.wikipedia.org/wiki/Grover%27s_algorithm) and quantum simulation algorithms.</span></span>
<span data-ttu-id="899f1-126">ここでは、振幅増幅とフェーズ推定の2つのアプリケーションに必要な oracles に焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="899f1-126">Here we focus on the oracles needed for just two applications: amplitude amplification and phase estimation.</span></span>
<span data-ttu-id="899f1-127">最初に、振幅増幅の oracles について説明してから、フェーズの推定に進みます。</span><span class="sxs-lookup"><span data-stu-id="899f1-127">We will first discuss amplitude amplification oracles before proceeding to phase estimation.</span></span>

### <a name="amplitude-amplification-oracles"></a><span data-ttu-id="899f1-128">振幅増幅 Oracles</span><span class="sxs-lookup"><span data-stu-id="899f1-128">Amplitude Amplification Oracles</span></span> ###

<span data-ttu-id="899f1-129">振幅増幅アルゴリズムは、状態の反射のシーケンスを適用して、初期状態と最終状態との間の回転を実行します。</span><span class="sxs-lookup"><span data-stu-id="899f1-129">The amplitude amplification algorithm aims to perform a rotation between an initial state and a final state by applying a sequence of reflections of the state.</span></span>
<span data-ttu-id="899f1-130">アルゴリズムを機能させるには、これらの状態の両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="899f1-130">In order for the algorithm to function, it needs a specification of both of these states.</span></span>
<span data-ttu-id="899f1-131">これらの仕様は、2つの oracles によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="899f1-131">These specifications are given by two oracles.</span></span>
<span data-ttu-id="899f1-132">これらの oracles は、入力を "ターゲット" サブ空間と "初期" サブ空間という2つのスペースに分割することで機能します。</span><span class="sxs-lookup"><span data-stu-id="899f1-132">These oracles work by breaking the inputs into two spaces, a "target" subspace and an "initial" subspace.</span></span>
<span data-ttu-id="899f1-133">Oracles は、このようなサブスペースを識別します。これは、p Li 演算子が2つのスペースを識別する方法と似ています。これらのスペースには、$ pm $1 フェーズを適用します。</span><span class="sxs-lookup"><span data-stu-id="899f1-133">The oracles identify such subspaces, similar to how Pauli operators identify two spaces, by applying a $\pm 1$ phase to these spaces.</span></span>
<span data-ttu-id="899f1-134">主な違いは、このアプリケーションではこれらのスペースが半分のスペースである必要がないことです。</span><span class="sxs-lookup"><span data-stu-id="899f1-134">The main difference is that these spaces need not be half-spaces in this application.</span></span>
<span data-ttu-id="899f1-135">また、これら2つのサブスペースは、通常は相互に排他的ではないことに注意してください。両方のスペースのメンバーであるベクターが存在します。</span><span class="sxs-lookup"><span data-stu-id="899f1-135">Also note that these two subspaces are not usually mutually exclusive: there will be vectors that are members of both spaces.</span></span>
<span data-ttu-id="899f1-136">この値が true でない場合、振幅増幅は影響を受けません。そのため、最初のサブ空間が対象のサブ空間と重複しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="899f1-136">If this were not true then amplitude amplification would have no effect so we need the initial subspace to have non-zero overlap with the target subspace.</span></span>

<span data-ttu-id="899f1-137">ここでは、次のアクションを実行するために定義されている\_$0 に $P するために、振幅増幅が必要になる最初の oracle について説明します。</span><span class="sxs-lookup"><span data-stu-id="899f1-137">We will denote the first oracle that we need for amplitude amplification to be $P\_0$, defined to have the following action.</span></span>  <span data-ttu-id="899f1-138">"Initial" サブ空間 $P\_0 \ket{x} =-\ket{x} $ のすべての州 $ \ket{x} $ と、このサブ空間に含まれていないすべての州 $ \ket{y} $ について、\_0 \ket{y} = \ket{y} $ $P ます。</span><span class="sxs-lookup"><span data-stu-id="899f1-138">For all states $\ket{x}$ in the "initial" subspace $P\_0 \ket{x} = -\ket{x}$ and for all states $\ket{y}$ that are not in this subspace we have $P\_0 \ket{y} = \ket{y}$.</span></span>
<span data-ttu-id="899f1-139">対象のサブ空間をマークする oracle ($P _1 $) は、まったく同じ形式になります。</span><span class="sxs-lookup"><span data-stu-id="899f1-139">The oracle that marks the target subspace, $P_1$, takes exactly the same form.</span></span>
<span data-ttu-id="899f1-140">ターゲットのサブ空間内のすべての州 $ \ket{x} $ (つまり、アルゴリズムによって出力されるすべての状態) に対して、$P _1 \ k {x} =-\ket{x} $ を使用します。</span><span class="sxs-lookup"><span data-stu-id="899f1-140">For all states $\ket{x}$ in the target subspace (i.e., for all states that you'd like the algorithm to output), $P_1\ket{x} = -\ket{x}$.</span></span>
<span data-ttu-id="899f1-141">同様に、対象のサブ空間に含まれていないすべての州 $ \ket{y} $ に対して、_1 \ k {y} = \ket{y} $ という $P ます。</span><span class="sxs-lookup"><span data-stu-id="899f1-141">Similarly, for all states $\ket{y}$ that are not in the target subspace $P_1\ket{y} = \ket{y}$.</span></span>
<span data-ttu-id="899f1-142">次に、これら2つの反射を結合して、施行 =-P_0 P_1 $ という $Q の1つの手順を実行する演算子を形成します。この場合、マイナス記号全体は、制御されたアプリケーションで考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="899f1-142">These two reflections are then combined to form an operator that enacts a single step of amplitude amplification, $Q = -P_0 P_1$, where the overall minus sign is only important to consider in controlled applications.</span></span>
<span data-ttu-id="899f1-143">次に、最初のサブ空間にある $ \ket{\psi} $ という初期状態を取得し、$ \ket{\psi} を実行してから、$ を実行します。</span><span class="sxs-lookup"><span data-stu-id="899f1-143">Amplitude amplification then proceeds by taking an initial state, $\ket{\psi}$ that is in the initial subspace and then performs $\ket{\psi} \mapsto Q^m \ket{\psi}$.</span></span>
<span data-ttu-id="899f1-144">このような反復処理を実行すると、最初の状態が、マークされたスペースを持つ $ \ sin ^ 2 (-シータ) $ と重複している場合、$ iteration を $m した後、この重複が $ \ sin ^ 2 ([2m + 1] \ シータ) $ になります。</span><span class="sxs-lookup"><span data-stu-id="899f1-144">Performing such an iteration guarantees that if one starts with an initial state that has overlap $\sin^2(\theta)$ with the marked space then after $m$ iterations this overlap becomes $\sin^2([2m + 1] \theta)$.</span></span>
<span data-ttu-id="899f1-145">そのため、通常は $ [2m + 1] \ シータ = \ pi/2 $; のような無料のパラメーターとして $m $ を選択する必要があります。ただし、このような剛体選択は、固定ポイントの振幅増幅など、一部の種類の振幅増幅では重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="899f1-145">We therefore typically wish to choose $m$ to be a free parameter such that $[2m+1]\theta = \pi/2$; however, such rigid choices are not as important for some forms of amplitude amplification such as fixed point amplitude amplification.</span></span>
<span data-ttu-id="899f1-146">このプロセスでは、quadratically を使用してマークされたサブ空間に状態を準備することができます。これは、限定機能に対するクエリの数を減らすとともに、厳密なクラシックデバイスでは実現できません。</span><span class="sxs-lookup"><span data-stu-id="899f1-146">This process allows us to prepare a state in the marked subspace using quadratically fewer queries to the marking function and the state preparation function than would be possible on a strictly classical device.</span></span>
<span data-ttu-id="899f1-147">これは、多くのアプリケーションがクォンタムコンピューティングを行う場合に、振幅増幅が大きなビルディングブロックであるためです。</span><span class="sxs-lookup"><span data-stu-id="899f1-147">This is why amplitude amplification is a significant building block for many applications of quantum computing.</span></span>

<span data-ttu-id="899f1-148">アルゴリズムの使用方法を理解するために、oracles の構築を可能にする例を提供すると便利です。</span><span class="sxs-lookup"><span data-stu-id="899f1-148">In order to understand how to use the algorithm, it is useful to provide an example that gives a construction of the oracles.</span></span>  <span data-ttu-id="899f1-149">この設定では、データベース検索に Grover のアルゴリズムを実行することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="899f1-149">Consider performing Grover's algorithm for database searches in this setting.</span></span>
<span data-ttu-id="899f1-150">Grover の検索では、目標は、状態 $ \ket{+} ^ {\ otimes n} = H ^ {/otimes n} \ket{0}$ を、(可能性がある) 多くのマークされた状態に変換することです。</span><span class="sxs-lookup"><span data-stu-id="899f1-150">In Grover's search the goal is to transform the state $\ket{+}^{\otimes n} = H^{\otimes n} \ket{0}$ into one of (potentially) many marked states.</span></span>
<span data-ttu-id="899f1-151">さらに簡単にするために、マークされた状態のみが $ \ket{0}$ であるケースを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="899f1-151">To further simplify, let's just look at the case where the only marked state is $\ket{0}$.</span></span>
<span data-ttu-id="899f1-152">次に、2つの oracles が用意されています。1つは、初期状態 $ \ket{+} ^ {\ otimes n} $ をマイナス記号付きでマークし、もう1つはマイナス記号を使用してマークされた状態 $ \ket{0}$ を負符号でマークします。</span><span class="sxs-lookup"><span data-stu-id="899f1-152">Then we have design two oracles: one that only marks the initial state $\ket{+}^{\otimes n}$ with a minus sign and another that marks the marked state $\ket{0}$ with a minus sign.</span></span>
<span data-ttu-id="899f1-153">2番目のゲートは、キャノンの制御フロー操作を使用して、次の処理操作を使用して実装できます。</span><span class="sxs-lookup"><span data-stu-id="899f1-153">The latter gate can be implemented using the following process operation, by using the control flow operations in the canon:</span></span>

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

<span data-ttu-id="899f1-154">この oracle は、<xref:microsoft.quantum.canon.rall1> 操作の特殊なケースで、リフレクションケース $ + phi = \ pi $ の代わりに任意のフェーズで回転できるようにします。</span><span class="sxs-lookup"><span data-stu-id="899f1-154">This oracle is then a special case of the <xref:microsoft.quantum.canon.rall1> operation, which allows for rotating by an arbitrary phase instead of the reflection case $\phi = \pi$.</span></span>
<span data-ttu-id="899f1-155">この場合、`RAll1` は <xref:microsoft.quantum.intrinsic.r1> 準備操作に似ています。これは、single qubit 状態 $ \ket{1}$ の代わりに $ \ket{11\cdots1} $ を回転させる点です。</span><span class="sxs-lookup"><span data-stu-id="899f1-155">In this case, `RAll1` is similar to the <xref:microsoft.quantum.intrinsic.r1> prelude operation, in that it rotates about $\ket{11\cdots1}$ instead of the single-qubit state $\ket{1}$.</span></span>

<span data-ttu-id="899f1-156">初期サブ空間をマークする oracle は同様に構築できます。</span><span class="sxs-lookup"><span data-stu-id="899f1-156">The oracle that marks the initial subspace can be constructed similarly.</span></span>
<span data-ttu-id="899f1-157">擬似コードで:</span><span class="sxs-lookup"><span data-stu-id="899f1-157">In pseudocode:</span></span>

1. <span data-ttu-id="899f1-158">すべての qubit に $ ゲート $H 適用します。</span><span class="sxs-lookup"><span data-stu-id="899f1-158">Apply $H$ gates to every qubit.</span></span>
2. <span data-ttu-id="899f1-159">すべての qubit に $ ゲート $X 適用します。</span><span class="sxs-lookup"><span data-stu-id="899f1-159">Apply $X$ gates to every qubit.</span></span>
3. <span data-ttu-id="899f1-160">$N ^ {\ text{th} $ qubit に $n $1 の $Z $-gate を適用します。</span><span class="sxs-lookup"><span data-stu-id="899f1-160">Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.</span></span>
4. <span data-ttu-id="899f1-161">すべての qubit に $ ゲート $X 適用します。</span><span class="sxs-lookup"><span data-stu-id="899f1-161">Apply $X$ gates to every qubit.</span></span>
5. <span data-ttu-id="899f1-162">すべての qubit に $ ゲート $H 適用します。</span><span class="sxs-lookup"><span data-stu-id="899f1-162">Apply $H$ gates to every qubit.</span></span>

<span data-ttu-id="899f1-163">今回は、前に説明した <xref:microsoft.quantum.canon.rall1> 操作と共に <xref:microsoft.quantum.canon.applywith> を使用する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="899f1-163">This time, we also demonstrate using <xref:microsoft.quantum.canon.applywith> together with the <xref:microsoft.quantum.canon.rall1> operation discussed above:</span></span>

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

<span data-ttu-id="899f1-164">次に、これら2つの oracles を組み合わせて、2つの状態の間を回転させ、$ \ket{+} ^ {-otimes n} $ を $ \ket{0}$ に変換します。これは、Hadamard ゲートの複数のレイヤーを使用して、$ \ sqrt{2 ^ n} $ に比例します。 (ie $m \、\ sqrt{2 ^ n} $) と約 $ 2 ^ n $ のレイヤーは、$ \ket{0}$ の状態を無作為に準備するために必要となります。これは、結果 $0 $ が観測されるまで、初期状態を準備して測定します。</span><span class="sxs-lookup"><span data-stu-id="899f1-164">We can then combine these two oracles together to rotate between the two states and deterministically transform $\ket{+}^{\otimes n}$ to $\ket{0}$ using a number of layers of Hadamard gates that is proportional to $\sqrt{2^n}$ (ie $m\propto \sqrt{2^n}$) versus the roughly $2^n$ layers that would be needed to non-deterministically prepare the $\ket{0}$ state by preparing and measuring the initial state until the outcome $0$ is observed.</span></span>

### <a name="phase-estimation-oracles"></a><span data-ttu-id="899f1-165">フェーズ推定 Oracles</span><span class="sxs-lookup"><span data-stu-id="899f1-165">Phase Estimation Oracles</span></span> ###

<span data-ttu-id="899f1-166">フェーズの推定では、oracles の方がやや自然です。</span><span class="sxs-lookup"><span data-stu-id="899f1-166">For phase estimation the oracles are somewhat more natural.</span></span>
<span data-ttu-id="899f1-167">フェーズの推定の目的は、ユニタリ行列の固有値からサンプリングできるサブルーチンを設計することです。</span><span class="sxs-lookup"><span data-stu-id="899f1-167">The aim in phase estimation is to design a subroutine that is capable of sampling from the eigenvalues of a unitary matrix.</span></span>
<span data-ttu-id="899f1-168">この方法は、化学およびマテリアルサイエンスの物理的な問題が多く発生しているため、この固有値は、次のフェーズ図に関する貴重な情報を提供する、量子システムの注ぎを提供します。分子の材料と反力のあるダイナミクス。</span><span class="sxs-lookup"><span data-stu-id="899f1-168">This method is indispensable in quantum simulation because for many physical problems in chemistry and material science these eigenvalues give the ground-state energies of quantum systems which provides us valuable information about the phase diagrams of materials and reaction dynamics for molecules.</span></span>
<span data-ttu-id="899f1-169">フェーズ推定のすべてのフレーバーには、入力のユニタリが必要です。</span><span class="sxs-lookup"><span data-stu-id="899f1-169">Every flavor of phase estimation needs an input unitary.</span></span>
<span data-ttu-id="899f1-170">このユニタリは、2種類の oracles のいずれかで記述された通常です。</span><span class="sxs-lookup"><span data-stu-id="899f1-170">This unitary is customarily described by one of two types of oracles.</span></span>

> [!TIP]
> <span data-ttu-id="899f1-171">これらのサンプルでは、次に示す oracle の両方の型について説明します。</span><span class="sxs-lookup"><span data-stu-id="899f1-171">Both of the oracle types described below are covered in the samples.</span></span>
> <span data-ttu-id="899f1-172">連続クエリ oracles の詳細については、 [ **PhaseEstimation**サンプル](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="899f1-172">To learn more about continuous query oracles, please see the [**PhaseEstimation** sample](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation).</span></span>
> <span data-ttu-id="899f1-173">離散クエリ oracles の詳細については、 [ **IsingPhaseEstimation**サンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="899f1-173">To learn more about discrete query oracles, please see the [**IsingPhaseEstimation** sample](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).</span></span>

<span data-ttu-id="899f1-174">Oracle の最初の種類は、個別のクエリとして oracle を呼び出し、ユーザー定義型の <xref:microsoft.quantum.oracles.discreteoracle>で表現します。ここでは、単に、インテキスト行列を使用します。</span><span class="sxs-lookup"><span data-stu-id="899f1-174">The first type of oracle, which we call a discrete query oracle and represent with the user-defined type <xref:microsoft.quantum.oracles.discreteoracle>, simply involves a unitary matrix.</span></span>
<span data-ttu-id="899f1-175">$U $ が、推定する値を持つユニタリの場合、$U $ の oracle は $U $ を実装するサブルーチンの単なるスタンドアロンです。</span><span class="sxs-lookup"><span data-stu-id="899f1-175">If $U$ is the unitary whose eigenvalues we wish to estimate then the oracle for $U$ is simply a stand-in for a subroutine that implements $U$.</span></span>
<span data-ttu-id="899f1-176">たとえば、$U $ は、前に定義した振幅推定用の oracle $Q $ になることがあります。</span><span class="sxs-lookup"><span data-stu-id="899f1-176">For example, one could take $U$ to be the oracle $Q$ defined above for amplitude estimation.</span></span>
<span data-ttu-id="899f1-177">このマトリックスの固有値を使用して、初期状態とターゲット状態の間の重複を推定することができます $ \ sin ^ 2 (quadratically) $。それ以外の場合に必要なサンプルの数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="899f1-177">The eigenvalues of this matrix can be used to estimate the overlap between the initial and target states, $\sin^2(\theta)$, using quadratically fewer samples than one would need otherwise.</span></span>
<span data-ttu-id="899f1-178">これにより、Grover oracle $Q $ を使用して、振幅推定のモニカーを入力として使用して、フェーズ推定の適用を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="899f1-178">This earns the application of phase estimation using the Grover oracle $Q$ as input the moniker of amplitude estimation.</span></span>
<span data-ttu-id="899f1-179">クォンタム metrology で広く使われているもう1つの一般的なアプリケーションでは、小さな回転角度を推定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="899f1-179">Another common application, widely used in quantum metrology, involves estimating a small rotation angle.</span></span>
<span data-ttu-id="899f1-180">つまり、$-シータ $ を推定して、$R _z (\ シータ) $ という形式の不明な回転ゲートを計算します。</span><span class="sxs-lookup"><span data-stu-id="899f1-180">In other words, we wish to estimate $\theta$ for an unknown rotation gate of the form $R_z(\theta)$.</span></span>
<span data-ttu-id="899f1-181">このような場合、ゲートの $ \ シータ $ という固定値を学習するために対話するサブルーチンは、$ $ \begin{align} U & = R_z (-シータ) \\\\ & = \begin{bmatrix} e ^ {-i-シータ/2} & 0 \\\\ 0 & e ^ {i/シータ/2} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="899f1-181">In such cases, the subroutine that we would interact with in order to learn this fixed value of $\theta$ for the gate is $$ \begin{align} U & = R_z(\theta) \\\\ & = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i\theta/2} \end{bmatrix}.</span></span>
<span data-ttu-id="899f1-182">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="899f1-182">\end{align} $$</span></span>

<span data-ttu-id="899f1-183">フェーズ推定で使用される oracle の2つ目の種類は、<xref:microsoft.quantum.oracles.continuousoracle> の種類で表される、oracle の連続クエリです。</span><span class="sxs-lookup"><span data-stu-id="899f1-183">The second type of oracle used in phase estimation is the continuous query oracle, represented by the <xref:microsoft.quantum.oracles.continuousoracle> type.</span></span>
<span data-ttu-id="899f1-184">フェーズ推定のための連続クエリ oracle では、$U (t) $ という形式を使用します。ここで $t $ はクラシックデプロイの既知の実数です。</span><span class="sxs-lookup"><span data-stu-id="899f1-184">A continuous query oracle for phase estimation takes the form $U(t)$ where $t$ is a classically known real number.</span></span>
<span data-ttu-id="899f1-185">$ を固定の $U にした場合、連続クエリ oracle では $U (t) = U ^ t $ という形式が使用されます。</span><span class="sxs-lookup"><span data-stu-id="899f1-185">If we let $U$ be a fixed unitary then the continuous query oracle takes the form $U(t) = U^t$.</span></span>
<span data-ttu-id="899f1-186">これにより、個別のクエリモデルに直接実装できなかった $-sqrt{u} $ などのマトリックスに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="899f1-186">This allows us to query matrices such as $\sqrt{U}$, which could not be implemented directly in the discrete query model.</span></span>

<span data-ttu-id="899f1-187">この種類の oracle は、特定のユニタリを調査していないが、そのために、ユニタリのジェネレーターのプロパティを学習する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="899f1-187">This type of oracle is valuable when you're not probing a particular unitary, but rather wish to learn the properties of the generator of the unitary.</span></span>
<span data-ttu-id="899f1-188">たとえば、dynamical クォンタムのシミュレーションでは、Hermitian $H 行列に対して $U (t) = e ^ {-i H t} $ を厳密に概算したクォンタム回線 ($ と進化時間 $t $) をシミュレートすることを目標としています。</span><span class="sxs-lookup"><span data-stu-id="899f1-188">For example, in dynamical quantum simulation the goal is to devise quantum circuits that closely approximate $U(t)=e^{-i H t}$ for a Hermitian matrix $H$ and evolution time $t$.</span></span>
<span data-ttu-id="899f1-189">$U (t) $ の固有値は、$H $ の固有値に直接関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="899f1-189">The eigenvalues of $U(t)$ are directly related to the eigenvalues of $H$.</span></span>
<span data-ttu-id="899f1-190">これを確認するには、$H $: $H \ket{E} = E\ket {E} $ の eigenvector を考えてみます。これにより、(t) \ket{E} = e ^ {i} \ k {E} = e ^ {-iEt} \ket{E} $ と $U いうマトリックス指数のパワーシリーズ定義から簡単に見ることができます。</span><span class="sxs-lookup"><span data-stu-id="899f1-190">To see this, consider an eigenvector of $H$: $H \ket{E} = E\ket{E}$ then it is easy to see from the power-series definition of the matrix exponential that $U(t) \ket{E} = e^{i\phi}\ket{E}= e^{-iEt}\ket{E}$.</span></span>
<span data-ttu-id="899f1-191">したがって、$U (t) $ の eigenphase を推定すると、eigenphase $E $ として eigenvector $ \ket{E} $ がフェーズ推定アルゴリズムに入力されます。</span><span class="sxs-lookup"><span data-stu-id="899f1-191">Thus estimating the eigenphase of $U(t)$ gives the eigenvalue $E$ assuming the eigenvector $\ket{E}$ is input into the phase estimation algorithm.</span></span>
<span data-ttu-id="899f1-192">ただし、この場合、$ $t の値はユーザーの裁量で選択できます。これは、$t $ の値が非常に小さい場合 $E $ は $E =-\ phi/t $ を使用して一意に反転できるためです。</span><span class="sxs-lookup"><span data-stu-id="899f1-192">However, in this case the value $t$ can be chosen at the user's discretion since for any sufficiently small value of $t$ the eigenvalue $E$ can be uniquely inverted through $E=-\phi/t$.</span></span>
<span data-ttu-id="899f1-193">クォンタムシミュレーションメソッドでは、小数部の進化を実行する機能が提供されているため、この方法では、単位の推定アルゴリズムによって、(特に、個別のクエリモデルでは、フォームの unitaries $U ^ j $ が許可されます。整数 $j $ に適用するには、連続クエリ oracle を使用すると、実際の値 $t $ に対して、$U ^ t $ という形式の unitaries 概算できます。</span><span class="sxs-lookup"><span data-stu-id="899f1-193">Since quantum simulation methods provide the ability to perform a fractional evolution, this grants phase estimation algorithms an additional freedom when querying the unitary, specifically while the discrete query model allows only unitaries of the form $U^j$ to applied for integer $j$ the continuous query oracle allows us to approximate unitaries of the form $U^t$ for any real valued $t$.</span></span>
<span data-ttu-id="899f1-194">これは、$E $; に関する最も多くの情報を提供する実験を正確に選択できるようにするため、フェーズの推定アルゴリズムから効率を上げるために重要です。個別のクエリに基づくメソッドでは、アルゴリズムで最適な数のクエリを選択することによって、危害を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="899f1-194">This is important to squeeze every last ounce of efficiency out of phase estimation algorithms because it allows us to choose precisely the experiment that would provide the most information about $E$; whereas methods based on discrete queries must make do with compromising by choosing the best integer number of queries in the algorithm.</span></span>

<span data-ttu-id="899f1-195">この具体的な例として、ゲートの回転角度ではなく、クォンタムシステムの procession 周波数を見積もることの問題について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="899f1-195">As a concrete example of this, consider the problem of estimating not the rotation angle of a gate but the procession frequency of a rotating quantum system.</span></span>
<span data-ttu-id="899f1-196">このような量子力学を説明するユニタリは $U (t) = R_z (2 \ オメガ t) $ で、進化時間 $t $ および不明な頻度 $ \ オメガ $ です。</span><span class="sxs-lookup"><span data-stu-id="899f1-196">The unitary that describes such quantum dynamics is $U(t)=R_z(2\omega t)$ for evolution time $t$ and unknown frequency $\omega$.</span></span>
<span data-ttu-id="899f1-197">このコンテキストでは、1つの $R _z $ gate を使用して任意の $t $ に対して $U (t) $ をシミュレートできます。そのため、このような場合は、個別のクエリのみを使用して、そのようにする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="899f1-197">In this context, we can simulate $U(t)$ for any $t$ using a single $R_z$ gate and as such do not need to restrict ourselves to only discrete queries to the unitary.</span></span>
<span data-ttu-id="899f1-198">このような連続モデルには、対数関数の分岐カットによってマスクされるフェーズ情報があるため、連続したクエリを使用するフェーズ推定プロセスから学習できるプロパティもあります。$t $ の非対応値に対して実行された実験の結果から明らかになります。</span><span class="sxs-lookup"><span data-stu-id="899f1-198">Such a continuous model also has the property that frequencies greater than $2\pi$ can be learned from phase estimation processes that use continuous queries because phase information that would otherwise be masked by the branch-cuts of the logarithm function can be revealed from the results of experiments performed on non-commensurate values of $t$.</span></span>
<span data-ttu-id="899f1-199">このため、このような連続したクエリモデル (フェーズ推定) の場合、oracle は適切なだけでなく、個別のクエリモデルにも適しています。</span><span class="sxs-lookup"><span data-stu-id="899f1-199">Thus for problems such as this continuous query models for the phase estimation oracle are not only appropriate but are also preferable to the discrete query model.</span></span>
<span data-ttu-id="899f1-200">このため、Q # には両方の形式のクエリの機能があり、ユーザーにそのまま残して、ニーズに合わせてフェーズの推定アルゴリズムを決定し、使用可能な oracle の種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="899f1-200">For this reason Q# has functionality for both forms of queries and leave it to the user to decide upon a phase estimation algorithm to fit their needs and the type of oracle that is available.</span></span>

## <a name="dynamical-generator-modeling"></a><span data-ttu-id="899f1-201">Dynamical Generator モデリング</span><span class="sxs-lookup"><span data-stu-id="899f1-201">Dynamical Generator Modeling</span></span> ##

<span data-ttu-id="899f1-202">時間の経過に伴うジェネレーターは、状態がどのように変化するかを示します。</span><span class="sxs-lookup"><span data-stu-id="899f1-202">Generators of time-evolution describe how states evolve through time.</span></span> <span data-ttu-id="899f1-203">たとえば、クォンタムの状態 $ \ket{\psi} $ の dynamics は、Schrödinger 式 $ $ \begin{align} i\ frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ によって制御されています。 Hermitian matrix $H $、Hamiltonian と呼ばれています。動く.</span><span class="sxs-lookup"><span data-stu-id="899f1-203">For instance, the dynamics of a quantum state $\ket{\psi}$ is governed by the Schrödinger equation $$ \begin{align} i\frac{d \ket{\psi(t)}}{d t} & = H \ket{\psi(t)}, \end{align} $$ with a Hermitian matrix $H$, known as the Hamiltonian, as the generator of motion.</span></span> <span data-ttu-id="899f1-204">初期状態が $ \ket{\psi (0)} $ at time $t = $0 の場合、この $t 式に対する正式なソリューションは、$ $ \begin{align} \ket{\psi (t)} = U (t) \ket{\psi (0)}, \end{align} $ $ となります。ここで、マトリックス指数 $U (t) = e ^ {-i H t} $ はと呼ばれます。ユニタリ時間の進化演算子。</span><span class="sxs-lookup"><span data-stu-id="899f1-204">Given an initial state $\ket{\psi(0)}$ at time $t=0$, the formal solution to this equation at time $t$ may be, in principle, written $$ \begin{align} \ket{\psi(t)} = U(t)\ket{\psi(0)}, \end{align} $$ where the matrix exponential $U(t)=e^{-i H t}$ is known as the unitary time-evolution operator.</span></span> <span data-ttu-id="899f1-205">次に、このフォームのジェネレーターに焦点を当てていますが、この概念は、開いているクォンタムシステムのシミュレーションや、より抽象的な差分式など、より広範に適用されることを重視しています。</span><span class="sxs-lookup"><span data-stu-id="899f1-205">Though we focus on generators of this form in the following, we emphasize that the concept applies more broadly, such as to the simulation of open quantum systems, or to more abstract differential equations.</span></span>

<span data-ttu-id="899f1-206">Dynamical シミュレーションの主な目的は、クォンタムコンピューターの qubits でエンコードされたクォンタムの状態に対して進化演算子を実装することです。</span><span class="sxs-lookup"><span data-stu-id="899f1-206">A primary goal of dynamical simulation is to implement the time-evolution operator on some quantum state encoded in qubits of a quantum computer.</span></span>  <span data-ttu-id="899f1-207">多くの場合、Hamiltonian は $d $ より単純な用語の合計に分割されることがあります。</span><span class="sxs-lookup"><span data-stu-id="899f1-207">In many cases, the Hamiltonian may be broken into a sum of some $d$ simpler terms</span></span>

<span data-ttu-id="899f1-208">$ $ \begin{align} H & = \ sum ^ {d-1} _ {j = 0} H_j, \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="899f1-208">$$ \begin{align} H & = \sum^{d-1}_{j=0} H_j, \end{align} $$</span></span>

<span data-ttu-id="899f1-209">各用語による時間の進化は、クォンタムコンピューターで簡単に実装できます。</span><span class="sxs-lookup"><span data-stu-id="899f1-209">where time-evolution by each term alone is easy to implement on a quantum computer.</span></span> <span data-ttu-id="899f1-210">たとえば、$H _j $ が、qubit レジスタ `qubits`の1番目と2番目の要素に対して動作する、$ 演算子 $X _1X_2 $ 演算子である場合、それによって発生する時間の増加は、シグネチャ $t を持つ操作 `Exp([PauliX,PauliX], t, qubits[1..2])`を呼び出すことによって簡単に実装できます。`((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`</span><span class="sxs-lookup"><span data-stu-id="899f1-210">For instance, if $H_j$ is a Pauli $X_1X_2$ operator acting on the 1st and 2nd elements of the qubit register `qubits`, time-evolution by it for any time $t$ may be implemented simply by calling the operation `Exp([PauliX,PauliX], t, qubits[1..2])`, which has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="899f1-211">Hamiltonian のシミュレーションで後ほど説明するように、1つの解決策として、$H $ による時間の進化にかかる時間を短縮することがあります。</span><span class="sxs-lookup"><span data-stu-id="899f1-211">As discussed later in Hamiltonian Simulation, one solution then is to approximate time-evolution by $H$ with a sequence of simpler operations</span></span>

<span data-ttu-id="899f1-212">$ $ \begin{align} U (t) & = \ left (e ^ {-iH\_0 t/r} e ^ {-iH\_1 t/r}/cドット e ^ {-iH\_{d-1} t/r} \ 右) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\|H\_j\\| ^ 2 t ^ 2/r)、\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="899f1-212">$$ \begin{align} U(t) & = \left( e^{-iH\_0 t / r} e^{-iH\_1 t / r} \cdots e^{-iH\_{d-1} t / r} \right)^{r} + \mathcal{O}(d^2 \max_j \\|H\_j\\|^2 t^2/r), \end{align} $$</span></span>

<span data-ttu-id="899f1-213">> $0 の整数 $r では、近似誤差を制御します。</span><span class="sxs-lookup"><span data-stu-id="899f1-213">where the integer $r > 0$ controls the approximation error.</span></span>

<span data-ttu-id="899f1-214">Dynamical generator モデリングライブラリは、単純なジェネレーターの観点から、複雑なジェネレーターを体系的にエンコードするためのフレームワークを提供します。</span><span class="sxs-lookup"><span data-stu-id="899f1-214">The dynamical generator modeling library provides a framework for systematically encoding complicated generators in terms of simpler generators.</span></span> <span data-ttu-id="899f1-215">そのような説明は、シミュレーションライブラリなどに渡すことによって、選択したシミュレーションアルゴリズムによって時間の進化を実装し、多くの詳細情報が自動的に処理されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="899f1-215">Such a description may then be passed to, say, the simulation library to implement time-evolution by a simulation algorithm of choice, with many details automatically taken care of.</span></span>

> [!TIP]
> <span data-ttu-id="899f1-216">以下で説明する dynamical generator ライブラリについては、「」のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="899f1-216">The dynamical generator library described below is covered in the samples.</span></span> <span data-ttu-id="899f1-217">整理モデルに基づく例については、「 [ **isinggenerators**のサンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/generators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="899f1-217">For an example based on the Ising model, please see the [**IsingGenerators** sample](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/generators).</span></span>
> <span data-ttu-id="899f1-218">分子 Hydrogen に基づく例については、 [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line)と[**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/gui)のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="899f1-218">For an example based on molecular Hydrogen, please see the [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) and [**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/gui) samples.</span></span>

### <a name="complete-description-of-a-generator"></a><span data-ttu-id="899f1-219">ジェネレーターの完全な説明</span><span class="sxs-lookup"><span data-stu-id="899f1-219">Complete Description of a Generator</span></span> ###

<span data-ttu-id="899f1-220">最上位レベルでは、Hamiltonian の完全な説明が、2つのコンポーネントを持つユーザー定義型 `EvolutionGenerator` に含まれています。</span><span class="sxs-lookup"><span data-stu-id="899f1-220">At the top level, a complete description of a Hamiltonian is contained in the `EvolutionGenerator` user-defined type which has two components.:</span></span>

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

<span data-ttu-id="899f1-221">`GeneratorSystem` のユーザー定義型は、Hamiltonian の古典的な説明です。</span><span class="sxs-lookup"><span data-stu-id="899f1-221">The `GeneratorSystem` user-defined type is a classical description of the Hamiltonian.</span></span>

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

<span data-ttu-id="899f1-222">組の最初の要素 `Int` は、$ $d $ という用語を Hamiltonian に格納します。2番目の要素 `(Int -> GeneratorIndex)` は、$\{0, 1,..., d-1\}$ の整数インデックスを、Hamiltonian 内の各プリミティブ項を一意に識別する `GeneratorIndex` ユーザー定義型にマップする関数です。</span><span class="sxs-lookup"><span data-stu-id="899f1-222">The first element `Int` of the tuple stores the number of terms $d$ in the Hamiltonian, and the second element `(Int -> GeneratorIndex)` is a function that maps an integer index in $\{0,1,...,d-1\}$ to a `GeneratorIndex` user-defined type which uniquely identifies each primitive term in the Hamiltonian.</span></span> <span data-ttu-id="899f1-223">Hamiltonian では、配列 `GeneratorIndex[]`ではなく関数として用語のコレクションを指定することによって、Hamiltonians を多数の用語で記述する場合に特に便利な、`GeneratorIndex` を実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="899f1-223">Note that by expressing the collection of terms in the Hamiltonian as a function rather than as an array `GeneratorIndex[]`, this allows for on-the-fly computation of the `GeneratorIndex` which is especially useful when describing Hamiltonians with a large number of terms.</span></span>

<span data-ttu-id="899f1-224">とてもでは、`GeneratorIndex` によって識別されるプリミティブ用語についての規則を適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="899f1-224">Crucially, we do not impose a convention on what primitive terms identified by the `GeneratorIndex` are easy-to-simulate.</span></span> <span data-ttu-id="899f1-225">たとえば、前に説明したように、プリミティブな用語は PFermionic の演算子にすることができますが、クォンタムの化学シミュレーションで一般的に使用される annihilation や作成演算子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="899f1-225">For instance, primitive terms could be Pauli operators as discussed above, but they could also be Fermionic annihilation and creation operators commonly used in quantum chemistry simulation.</span></span> <span data-ttu-id="899f1-226">`GeneratorIndex` は意味がありません。これは、ポイントした期間による時間の進化が、クォンタム回線として実装されている可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="899f1-226">By itself, a `GeneratorIndex` is meaningless as it does not describe how time-evolution by the term it points to may be implemented as a quantum circuit.</span></span>

<span data-ttu-id="899f1-227">これは、一部の正規セットから描画されたすべての `GeneratorIndex`を、クォンタム回線として表現される `EvolutionUnitary`である `EvolutionSet` をマップするユーザー定義型を指定することによって解決されます。</span><span class="sxs-lookup"><span data-stu-id="899f1-227">This is resolved by specifying an `EvolutionSet` user-defined type that maps any `GeneratorIndex`, drawn from some canonical set, to a unitary operator, the `EvolutionUnitary`, expressed as a quantum circuit.</span></span> <span data-ttu-id="899f1-228">`EvolutionSet` は、`GeneratorIndex` の構成方法の規則を定義し、可能な `GeneratorIndex`のセットも定義します。</span><span class="sxs-lookup"><span data-stu-id="899f1-228">The `EvolutionSet` defines the convention of how a `GeneratorIndex` is structured, and also defines the set of possible `GeneratorIndex`.</span></span>

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a><span data-ttu-id="899f1-229">P# li 演算子ジェネレーター</span><span class="sxs-lookup"><span data-stu-id="899f1-229">Pauli Operator Generators</span></span> ###

<span data-ttu-id="899f1-230">ジェネレーターの具体例としては、Hamiltonians 演算子の合計であり、それぞれ異なる係数を持つことがあります。</span><span class="sxs-lookup"><span data-stu-id="899f1-230">A concrete and useful example of generators are Hamiltonians that are a sum of Pauli operators, each possibly with a different coefficient.</span></span>
<span data-ttu-id="899f1-231">$ $ \begin{align} H & = \ sum ^ {d-1} _ {j = 0} a_j H_j, \end{align} $ $。各 H_j $ $ $ は、現在、p Li グループから描画されています。</span><span class="sxs-lookup"><span data-stu-id="899f1-231">$$ \begin{align} H & = \sum^{d-1}_{j=0} a_j H_j, \end{align} $$ where each $\hat H_j$ is now drawn from the Pauli group.</span></span> <span data-ttu-id="899f1-232">このようなシステムでは、`EvolutionSet` 型の `PauliEvolutionSet()` を提供しています。これにより、次のシグネチャを持つ、`GeneratorIndex`によって、Pan Li グループと係数の要素が識別される方法に関する規則が定義されます。</span><span class="sxs-lookup"><span data-stu-id="899f1-232">For such systems, we provide the `PauliEvolutionSet()` of type `EvolutionSet` that defines a convention for how an element of the Pauli group and a coefficient may be identified by a `GeneratorIndex`, which has the following signature.</span></span>

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

<span data-ttu-id="899f1-233">このエンコードでは、最初のパラメーター `Int[]` は、PI\rightarrow Li 文字列を指定します。ここで、$ & hat $0、$、hat X\rightarrow $1、$/hat Y\rightarrow $2、および $/hat Z\rightarrow $3 です。</span><span class="sxs-lookup"><span data-stu-id="899f1-233">In our encoding, the first parameter `Int[]` specifies a Pauli string, where $\hat I\rightarrow 0$, $\hat X\rightarrow 1$, $\hat Y\rightarrow 2$, and $\hat Z\rightarrow 3$.</span></span> <span data-ttu-id="899f1-234">2番目のパラメーター `Double[]` は、Hamiltonian 内の p Li 文字列の係数を格納します。</span><span class="sxs-lookup"><span data-stu-id="899f1-234">The second parameter `Double[]` stores the coefficient of the Pauli string in the Hamiltonian.</span></span> <span data-ttu-id="899f1-235">この配列の最初の要素のみが使用されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="899f1-235">Note that only the first element of this array is used.</span></span> <span data-ttu-id="899f1-236">3番目のパラメーターは、この P`Int[]` Li 文字列が処理する qubits のインデックスを作成し、重複する要素を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="899f1-236">The third parameter `Int[]` indexes the qubits that this Pauli string acts on, and must have no duplicate elements.</span></span> <span data-ttu-id="899f1-237">したがって、Hamiltonian term $0.4 \ hat X_0; hat Y_8/hat I_2/hat Z_1 $ は、</span><span class="sxs-lookup"><span data-stu-id="899f1-237">Thus the Hamiltonian term $0.4 \hat X_0 \hat Y_8\hat I_2\hat Z_1$ may be represented as</span></span>

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

<span data-ttu-id="899f1-238">`PauliEvolutionSet()` は、このフォームのすべての `GeneratorIndex` を、次のシグネチャを持つ `EvolutionUnitary` にマップする関数です。</span><span class="sxs-lookup"><span data-stu-id="899f1-238">The `PauliEvolutionSet()` is a function that maps any `GeneratorIndex` of this form to an `EvolutionUnitary` with the following signature.</span></span>

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

<span data-ttu-id="899f1-239">1番目のパラメーターは、時間の長さを表します。これには、`GeneratorIndex`の係数で乗算されます。</span><span class="sxs-lookup"><span data-stu-id="899f1-239">The first parameter represents a time-duration, that will be multiplied by the coefficient in the `GeneratorIndex`, of unitary evolution.</span></span> <span data-ttu-id="899f1-240">2番目のパラメーターは、ユニタリが動作する qubit レジスタです。</span><span class="sxs-lookup"><span data-stu-id="899f1-240">The second parameter is the qubit register the unitary acts on.</span></span> 

### <a name="time-dependent-generators"></a><span data-ttu-id="899f1-241">時間に依存するジェネレーター</span><span class="sxs-lookup"><span data-stu-id="899f1-241">Time-Dependent Generators</span></span> ###

<span data-ttu-id="899f1-242">多くの場合、モデリングの時間に依存するジェネレーターにも興味があります。これは、Schrödinger 式 $ $ \begin{align} i\ frac {d \ket{\psi (t)}} {d t} & = \ hat H (t) \ket{\psi (t)}, \end{align} $ $ (ジェネレーター $ \ hat H (t) $ が現在) で発生します。時間に依存します。</span><span class="sxs-lookup"><span data-stu-id="899f1-242">In many cases, we are also interested in modelling time-dependent generators, as might occur in the Schrödinger equation $$ \begin{align} i\frac{d \ket{\psi(t)}}{d t} & = \hat H(t) \ket{\psi(t)}, \end{align} $$ where the generator $\hat H(t)$ is now time-dependent.</span></span> <span data-ttu-id="899f1-243">この場合、上記の時間に依存しないジェネレーターからの拡張機能は簡単です。</span><span class="sxs-lookup"><span data-stu-id="899f1-243">The extension from the time-independent generators above to this case is straightforward.</span></span> <span data-ttu-id="899f1-244">$ $T すべての時刻の Hamiltonian を説明する固定 `GeneratorSystem` ではなく、ユーザー定義型 `GeneratorSystemTimeDependent` を使用します。</span><span class="sxs-lookup"><span data-stu-id="899f1-244">Rather than having a fixed `GeneratorSystem` describing the Hamiltonian for all times $t$, we instead have the `GeneratorSystemTimeDependent` user-defined type.</span></span>

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

<span data-ttu-id="899f1-245">1番目のパラメーターは、[0, 1] $ の連続スケジュールパラメーター $s です。この型の関数は、そのスケジュールの `GeneratorSystem` を返します。</span><span class="sxs-lookup"><span data-stu-id="899f1-245">The first parameter is a continuous schedule parameter $s\in [0,1]$, and functions of this type return a `GeneratorSystem` for that schedule.</span></span> <span data-ttu-id="899f1-246">Schedule パラメーターは、$s = t/T $ のような物理時刻パラメーターに線形的に関連付けられている可能性があることに注意してください (例: シミュレーション $T $ の合計時間)。</span><span class="sxs-lookup"><span data-stu-id="899f1-246">Note that the schedule parameter may be linearly related to the physical time parameter e.g. $s = t / T$, for some total time of simulation $T$.</span></span> <span data-ttu-id="899f1-247">ただし、通常はそうではありません。</span><span class="sxs-lookup"><span data-stu-id="899f1-247">In general however, this need not be the case.</span></span>

<span data-ttu-id="899f1-248">同様に、このジェネレーターの完全な説明には `EvolutionSet`が必要であるため、`EvolutionSchedule` ユーザー定義型を定義します。</span><span class="sxs-lookup"><span data-stu-id="899f1-248">Similarly, a complete description of this generator requires an `EvolutionSet`, and so we define an `EvolutionSchedule` user-defined type.</span></span>

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
