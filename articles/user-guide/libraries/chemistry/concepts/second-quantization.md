---
title: 2番目の量子化
description: クォンタムプログラミングで電子構造をモデル化するための2番目の量子化アプローチについて説明します。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: e17c97767b05395af46a82c4035337406c7e3218
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276106"
---
# <a name="second-quantization"></a><span data-ttu-id="8a9a2-103">2番目の量子化</span><span class="sxs-lookup"><span data-stu-id="8a9a2-103">Second Quantization</span></span>

<span data-ttu-id="8a9a2-104">2番目の量子化では、別のレンズによって電子構造の問題を確認します。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-104">Second quantization looks at the problem of electronic structure through a different lens.</span></span>
<span data-ttu-id="8a9a2-105">各 $N _e $ 原子を特定の状態 (または回転) に割り当てるのではなく、2番目の量子化で各回転を追跡し、各に電子が存在するかどうかを保存し、同時に、対応する wave 関数の対称プロパティを自動的に確保します。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-105">Rather than assigning each of the $N_e$ electrons to a specific state (or orbital), second quantization tracks each orbital and stores whether there is an electron present in each of them and at the same time automatically ensures symmetry properties of the corresponding wave function.</span></span>
<span data-ttu-id="8a9a2-106">これは、入力状態の symmetrizing を気にすることなく、量子化学モデルを指定できるようにするために重要です。また、2つ目の量子化では、小さなクォンタムコンピューターを使用してこのようなモデルをシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-106">This is important because it allows quantum chemistry models to be specified without having to worry about anti-symmetrizing the input state (as is required for fermions) and also because second quantization allows such models to be simulated using small quantum computers.</span></span>

<span data-ttu-id="8a9a2-107">2番目の量子化の例として、$ \ psi_0/cドット \ psi_ {N-1} $ が空間 orbitals の orthonormal セットであるとします。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-107">As an example of second quantization in action, let's assume that $\psi_0\cdots \psi_{N-1}$ are an orthonormal set of spatial orbitals.</span></span>
<span data-ttu-id="8a9a2-108">これらの方法は、考慮された有限の基準でシステムをできるだけ正確に表すように選択されています。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-108">These orbitals are chosen to represent the system as accurately as possible within the finite basis set considered.</span></span>
<span data-ttu-id="8a9a2-109">このような場合の一般的な例としては、hydrogen atom の eigenbasis を形成する atomic orbitals があります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-109">A common example of such orbitals are atomic orbitals which form an eigenbasis for the hydrogen atom.</span></span>
<span data-ttu-id="8a9a2-110">原子には2つのスピン状態があるため、2つの原子を各空間回転にぎゅうぎゅうできます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-110">Because electrons have two spin states, two electrons can be crammed into each such spatial orbital.</span></span>
<span data-ttu-id="8a9a2-111">つまり、有効なベースの状態は $ \ psi_ {0 の形式になります。 \uparrow}、\uparrow}、\ psi_ {N-1、、\ psi_ {0, \ downarrow}, \ lドット, \ psi_ {N-1, \ downarrow} $ ここで、$ \uparrow $ と $ $ は、スピンの自由度の2つの eigenstates を指定するラベルです。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-111">That is to say, the valid basis states are of the form $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ where $\uparrow$ and $\downarrow$ are labels that specify the two eigenstates of the spin degree of freedom.</span></span>
<span data-ttu-id="8a9a2-112">$ (J,-シグマ) $ for $ \uparrow, 回転のこの結合インデックス \{ \} は、空間とスピンの自由度の両方を格納するため、スピンと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-112">This combined index of $(j,\sigma)$ for $\sigma \in \{\uparrow,\downarrow\}$ is called a spin-orbital because it stores both the spatial as well as the spin degree of freedom.</span></span>
<span data-ttu-id="8a9a2-113">化学ライブラリでは、スピン orbitals はデータ構造に格納され、次のように作成され `SpinOrbital` ます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-113">In the chemistry library, spin-orbitals are stored in a `SpinOrbital` data structure, and are created as follows.</span></span>

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

<span data-ttu-id="8a9a2-114">これは、wave 関数のスピンと空間の両方の部分を、$ \ psi_ \ ドット \ psi_ {2N-1} $ として正式に考えることができることを意味し {0} ます。ここでは、各インデックスが $ (j,-シグマ) $ の列挙体です。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-114">This means that we can formally think of the basis for both the spin and spatial part of the wave function as $\psi_{0} \cdots \psi_{2N-1}$ where each of the indices now is an enumeration of a $(j,\sigma)$.</span></span>
<span data-ttu-id="8a9a2-115">考えられる列挙の1つとして、$g (j,-シグマ) = j + n \ シグマ ' $ があります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-115">One possible enumeration is $g(j,\sigma) = j+N\sigma'$.</span></span>
<span data-ttu-id="8a9a2-116">もう1つの考えられる列挙は $h (j, \ シグマ) = 2 \* j +-シグマ $ です。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-116">Another possible enumeration is $h(j,\sigma) = 2\*j + \sigma$.</span></span>
<span data-ttu-id="8a9a2-117">Quantum の化学ライブラリでは、これらの規則を使用できます。このようなエンコーディングでは、スピン orbitals は次のようにインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-117">The quantum chemistry library can use these conventions, and the spin-orbitals in such an encoding can be instantiated as follows.</span></span>

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

<span data-ttu-id="8a9a2-118">Fermionic システムの場合、P# li 除外の原則を使用すると、1つのスピン回転に複数の電子日が同時に存在するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-118">For fermionic systems, the Pauli exclusion principle prevents more than one electron from being present in any spin-orbital at the same time.</span></span>
<span data-ttu-id="8a9a2-119">つまり、$ \ psi_1 $ as \ begin{\begin{cases}} \ psi_1 \rightarrow \ket {0} _1 &-$ \ psi_1 $ が使用されていない場合、この2つの有効な状態を書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-119">This means that we can write the two legal states for $\psi_1$ as \begin{equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $\psi_1$ is not occupied,} </span></span>\\\
<span data-ttu-id="8a9a2-120">{1}$ \ psi_1 $ が占有されている場合、\ket _1 & \ text{</span><span class="sxs-lookup"><span data-stu-id="8a9a2-120">\ket{1}_1 & \text{if $\psi_1$ is occupied.}</span></span> <span data-ttu-id="8a9a2-121">\end{cases}、このエンコードは、1つのクォンタムビットとして電子職業を格納できることを意味するため、quantum コンピューターには適しています。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-121">\end{cases} \end{equation} This encoding is great for quantum computers because it means that we can store the electronic occupation as a single quantum bit.</span></span>

<span data-ttu-id="8a9a2-122">$ 2N $ spin orbitals の職業状態は、同様に $ 2N $ qubits に格納できます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-122">The occupation states for the $2N$ spin orbitals can similarly be stored in $2N$ qubits.</span></span>
<span data-ttu-id="8a9a2-123">例として、$N = $2 の場合は、$ $ \ket {0} \ket {1} \ket {1} \ket {0} , $ $ という状態になります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-123">As an example, if $N=2$ then the state $$ \ket{0} \ket{1} \ket{1} \ket{0}, $$</span></span>

<span data-ttu-id="8a9a2-124">は、剰余が空であるスピン orbitals $1 $ と $2 $ に対応します。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-124">would correspond to spin orbitals $1$ and $2$ being occupied with the remainder empty.</span></span>
<span data-ttu-id="8a9a2-125">同様に、state $ $ \ket {0} \equiv \ket {0} _ {0} \ cドット \ket {0} _{N-1}, $ $</span><span class="sxs-lookup"><span data-stu-id="8a9a2-125">Similarly, the state $$ \ket{0} \equiv \ket{0}_{0} \cdots \ket{0}_{N-1}, $$</span></span>

<span data-ttu-id="8a9a2-126">には原子がなく、"vacuum state" と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-126">has no electrons and is known as the 'vacuum state'.</span></span>

<span data-ttu-id="8a9a2-127">2番目の量子化の美しい副作用は、クォンタム状態のアンチ対称性を明示的に追跡する必要がなくなることです。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-127">A beautiful side-effect of second quantization is that we no longer have to explicitly keep track of the anti-symmetry of the quantum state.</span></span>
<span data-ttu-id="8a9a2-128">これは、ここで説明するように、状態のアンチ対称性は、スピン回転の電子職業を作成および破棄する演算子の交換規則によって、それ自体を表します。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-128">This is because, as we will see, the anti-symmetry of the state represents itself instead through the anti-commutation rules of the operators that create and destroy electronic occupations of a spin orbital.</span></span>

## <a name="fermionic-operators"></a><span data-ttu-id="8a9a2-129">Fermionic 演算子</span><span class="sxs-lookup"><span data-stu-id="8a9a2-129">Fermionic operators</span></span>

<span data-ttu-id="8a9a2-130">2番目の量子化ベクトルに作用する2つの基本的な演算子を、作成演算子と annihilation 演算子と呼びます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-130">The two fundamental operators that act on the second-quantized basis vectors are known as creation and annihilation operators.</span></span>
<span data-ttu-id="8a9a2-131">これらの演算子は、特定の場所で原子を挿入または破棄します。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-131">These operators insert or destroy electrons at a particular location.</span></span>
<span data-ttu-id="8a9a2-132">これらは、それぞれ ^ \ dagger_j $ と $a _j $ $a 示されています。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-132">These are denoted $a^\dagger_j$ and $a_j$ respectively.</span></span>

<span data-ttu-id="8a9a2-133">たとえば、\begin{align} a ^ \ dagger_1 \ket {0} _1 = \ket {1} _1, \ クワッド a ^ \ dagger_1 \ket {1} _1 = 0, \ クワッド a_1 \ket _1 = {0} 0, \ quad a_1 \ket {1} _1 = \ket {0} _1.</span><span class="sxs-lookup"><span data-stu-id="8a9a2-133">For example, \begin{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,\quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span></span>
<span data-ttu-id="8a9a2-134">\end{align} ここでは、^ dagger_1 \ket {1} _1 = 0 $、$a _1 \ket {0} _1 $ を $a、0ベクトルではなく $ \ket _1 $ を生成することに注意して {0} ください。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-134">\end{align} Note that here $a^\dagger_1 \ket{1}_1=0$ and $a_1 \ket{0}_1$ yield the zero-vector not $\ket{0}_1$.</span></span>
<span data-ttu-id="8a9a2-135">そのため、このような演算子は Hermitian もユニタリでもありません。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-135">Such operators are therefore neither Hermitian nor unitary.</span></span>
<span data-ttu-id="8a9a2-136">型を使用して、一般的な作成演算子と annihilation 演算子を表し <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> ます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-136">We represent general creation and annihilation operators using the <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span></span>
<span data-ttu-id="8a9a2-137">たとえば、1つの作成演算子は、次のように表されます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-137">For instance, a single creation operator is represented as follow.</span></span>

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

<span data-ttu-id="8a9a2-138">また、このような演算子を使用すると、$ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 a ^ dagger_2 \ket {0} ^ {/otimes 4} を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-138">Also using such operators we can express $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}^{\otimes 4}.</span></span>
<span data-ttu-id="8a9a2-139">$ $ この一連の演算子は、前述の単一スピン回転ケースと同様の C# コードを使用して、Hamiltonian シミュレーションライブラリ内に構築されます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-139">$$ This sequence of operators would be constructed within the Hamiltonian simulation library using C# code that is similar to the single-spin orbital case considered above above:</span></span>
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

<span data-ttu-id="8a9a2-140">$K $ があるシステムの場合、2番目の量子化では、作成演算子 $a ^ \ dagger_i $ が $ $ a ^ \ dagger_i \ket{n_1、n_2、\ lドット、0_i、\ lドット、n_k} = (-1) ^ {S_i} \ket{n_1、n_2、\ lドット、1_i、\ lドット、n_k}、$ $ および $ $ a ^ dagger_i \ket{n_1、n_2、\ lドット、1_i、\ l点線、n_k} = 0、$ $ where $S _i = \ sum_ {j<i} a ^ dagger_j a_j $ は、1つのパーティクルの状態にあり、インデックス $j i $ を持つ、すべての対象の合計数を測定します。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-140">For a system of $k$ Fermions, in second quantization the action of the creation operator $a^\dagger_i$ is given by $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $$ and $$ a^\dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k } = 0, $$ where $S_i = \sum_{j<i} a^\dagger_j a_j$ measures the total number of Fermions that are in the state of a single particle and that have an index $j < i$.</span></span>

<span data-ttu-id="8a9a2-141">3番目の演算子は、2番目の量子表現でもよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-141">A third operator is also often used in second quantized representations.</span></span>
<span data-ttu-id="8a9a2-142">この演算子は、数値演算子として知られています。また、この演算子は、& lt; n_i = a ^ \ dagger_i a_i で定義されています。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-142">This operator is known as the number operator and is defined by \begin{equation} n_i = a^\dagger_i a_i.</span></span>
<span data-ttu-id="8a9a2-143">\ end{\begin{align}} この演算子は、指定されたスピン回転の職業をカウントします。これは、n_i {0} _i \ket &= 0 \ nonumber になります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-143">\end{equation} This operator counts the occupation of a given spin orbital, which is to say \begin{align} n_i \ket{0}_i &= 0\nonumber</span></span>\\\
<span data-ttu-id="8a9a2-144">n_i \ket {1} _i &= \ket {1} _i。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-144">n_i \ket{1}_i &= \ket{1}_i.</span></span>
<span data-ttu-id="8a9a2-145">\end{align} の例と同様に `FermionTerm` 、この数値演算子は次のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-145">\end{align} Similar to the above `FermionTerm` examples, this number operator is constructed as follows.</span></span>
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

<span data-ttu-id="8a9a2-146">はらみは、fermionic システムで作成または annihilation 演算子を使用した場合には明らかになります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-146">A subtlety emerges though when using creation or annihilation operators in fermionic systems.</span></span>
<span data-ttu-id="8a9a2-147">ラベルの交換では、有効なクォンタムの状態はすべてアンチ対称である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-147">We require that any valid quantum state is anti-symmetric under exchange of labels.</span></span>
<span data-ttu-id="8a9a2-148">つまり、$ $ a ^ dagger_2 a ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} です。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-148">This means that $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span></span>
<span data-ttu-id="8a9a2-149">$ $ このような演算子は ' commute ' $i と呼ばれます。 j $ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) a ^ \ dagger_j a ^ \ dagger_i、\ quad a ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i です。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-149">$$ Such operators are said to 'anti-commute' and in general for any $i, j$ we have that \begin{align} a^\dagger_i a^\dagger_j  = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,\quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span></span>
<span data-ttu-id="8a9a2-150">したがって、次の2つの <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> インスタンスは等価でないと見なされます。 \end{align}</span><span class="sxs-lookup"><span data-stu-id="8a9a2-150">\end{align} Thus the following two <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances are considered inequivalent</span></span>
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

<span data-ttu-id="8a9a2-151">各作成演算子の commute では、2つ目の量子表現を使用することによって、取り除くのアンチ対称性によって生じる課題が生じることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-151">The requirement that each of the creation operators anti-commute means that using a second quantized representation does obviate the challenges faced by the anti-symmetry of Fermions.</span></span>
<span data-ttu-id="8a9a2-152">代わりに、作成演算子の定義で問題を再現します。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-152">Instead the challenge re-emerges in our definition of the creation operators.</span></span> 

<span data-ttu-id="8a9a2-153">交換の規則を使用すると、一部のインスタンスが実際には `LadderSequence` 同じシーケンスの fermionic 演算子に対応し、場合によってはマイナス記号が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-153">Using the anti-commutation rules, some `LadderSequence` instances actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="8a9a2-154">たとえば、Hamiltonian $a 0 ^ \ ダガー a_1 ^ \ ダガー a_1 a_0 =-a_1 ^ \ ダガー a_0 ^ \ ダガー a_1 a_0 $ とします。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-154">For instance, consider the Hamiltonian $a_0^\dagger a_1^\dagger a_1 a_0 = - a_1^\dagger a_0^\dagger a_1 a_0$.</span></span>
<span data-ttu-id="8a9a2-155">これにより、すべてのに対して標準の順序を定義するため `FermionTerm` ます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-155">This motivates us to define a canonical ordering for every `FermionTerm`.</span></span>
<span data-ttu-id="8a9a2-156">次のよう `FermionTerm` に、が自動的に正規の順序で配置されます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-156">Any `FermionTerm` is automatically put into canonical order as follows.</span></span>
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a><span data-ttu-id="8a9a2-157">2番目-量子化 Fermionic Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="8a9a2-157">Second-Quantized Fermionic Hamiltonian</span></span>

<span data-ttu-id="8a9a2-158">[たとえば、電子システムのクォンタムモデル](xref:microsoft.quantum.chemistry.concepts.quantummodels)の Hamiltonian は、作成演算子と annihilation 演算子の観点から記述できます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-158">It is perhaps unsurprising that the Hamiltonian in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) can be written in terms of creation and annihilation operators.</span></span>
<span data-ttu-id="8a9a2-159">特に、$ \ psi \_ j $ が、基礎を形成するスピン orbitals の場合、</span><span class="sxs-lookup"><span data-stu-id="8a9a2-159">In particular, if $\psi\_j$ are the spin orbitals that form the basis then</span></span>

<span data-ttu-id="8a9a2-160">\ begin{nuc} \hat{H} = \ sum \_ {pq} h \_ {pq} a ^ \_ -ダガー p a \_ q +-frac {1} {2} -sum \_ {pqrs} H \_ {pqrs} a ^-ダガー \_ p a ^ \ ダガー \_ q a \_ ra \_ s + h \_ {\t extrm}, \ label{eq: totalHam} \ end{}。ここで $h \_ {\t extrm nuc} $ は核エネルギー (Oppenheimer 近似の定数) で、</span><span class="sxs-lookup"><span data-stu-id="8a9a2-160">\begin{equation} \hat{H} = \sum\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} where $h\_{\textrm nuc}$ is the nuclear energy (which is a constant under the Born-Oppenheimer approximation) and</span></span>

<span data-ttu-id="8a9a2-161">\begin{align} h \_ {pq} &= \ int \_ {-\ inf}} ^ \ inf\ psi ^ \* \_ p (x \_ 1) \ left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \ right) \ psi \_ q (x \_ 1) \mathrm{d} ^ 3x \_ 1, \end{align}</span><span class="sxs-lookup"><span data-stu-id="8a9a2-161">\begin{align} h\_{pq} &= \int\_{-\infty}^\infty \psi^\*\_p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\right)  \psi\_q(x\_1)\mathrm{d}^3x\_1, \end{align}</span></span>

<span data-ttu-id="8a9a2-162">ここで $V (x) $ は潜在的な平均フィールドです。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-162">where $V(x)$ is the mean-field potential, and</span></span>

<span data-ttu-id="8a9a2-163">\begin{align} h \_ {pqrs} &= \ int \_ {---{-\ inf} ^ \ inf\ int \_ {-\ (& a) {-/inf} ^ \_ \* (x \_ 1) \ psi \_ q ^ \* (x \_ 2) \ 左 (\ frac {1} {| x_1-x_2 |} \ 右) \ psi \_ r (x \_ 2) \ psi \_ s (x \_ 1) \mathrm{d} ^ 3x \_ 1 \ mathrm {d} ^ 3x \_ 2. \ label {eq: 積分} \end{align}</span><span class="sxs-lookup"><span data-stu-id="8a9a2-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\infty \int\_{-\infty}^\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{|x_1-x_2|} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq:integrals} \end{align}</span></span>

<span data-ttu-id="8a9a2-164">$H {pq} $ という用語は1つの \_ 原子と呼ばれています。これは、このようなすべての用語には単一のが関係していて、同様に $h \_ {pqrs} $ が2つの電子積分であるためです。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-164">The terms $h\_{pq}$ are referred to as one-electron integrals because all such terms only involve single electrons and likewise $h\_{pqrs}$ are the two-electron integrals.</span></span>
<span data-ttu-id="8a9a2-165">これらの係数の値を計算するには整数が必要であるため、これらは "積分" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-165">They are called integrals because computing the values of these coefficients requires an integral.</span></span>
<span data-ttu-id="8a9a2-166">1つの電子項は、個々の原子の kinetic エネルギーと、nuclei の電気フィールドとの相互作用を示しています。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-166">The one electron terms describe the kinetic energy of the individual electrons and their interactions with the electric fields of the nuclei.</span></span>
<span data-ttu-id="8a9a2-167">もう一方の2つの電子積分は、原子間の相互作用を記述します。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-167">The two-electron integrals on the other hand describe the interactions between the electrons.</span></span>

<span data-ttu-id="8a9a2-168">これらの用語の意味については、それぞれを構成する作成と annihilation の演算子から得られる直感があります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-168">An intuition for what these terms mean can be gleaned from the creation and annihilation operators that comprise each of them.</span></span>
<span data-ttu-id="8a9a2-169">たとえば $h _ {pq} a ^ dagger_p a_q $ は、スピン回転 $q $ からスピン回転 $p $ までの電子ホッピングを記述します。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-169">For example, $h_{pq}a^\dagger_p a_q$ describes the electron hopping from spin orbital $q$ to spin orbital $p$.</span></span>
<span data-ttu-id="8a9a2-170">同様に、_ {pqrs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (distinct $p、q、r、s $) では、原子2つのがスピン orbitals $r $ に記述さ $h れています。また、これらは、それぞれがスピン orbitals $s $ と $p $ で終了します。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-170">Similarly, the term $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (for distinct $p,q,r,s$) describes two electrons in spin orbitals $r$ and $s$ scattering off of each other and ending up in spin orbitals $p$ and $q$.</span></span>
<span data-ttu-id="8a9a2-171">$R = q $ および $p = s $ に $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ によって、互いに近くにある2つの原子に関連するエネルギーペナルティが与えられますが、dynamical プロセスについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-171">If $r=q$ and $p=s$ then $h_{prrp} a^\dagger_p a^\dagger_r a_r a_p = h_{prrp} n_p n_r$ gives the energy penalty associated with the two electrons being near each other, but does not describe a dynamical process.</span></span>

<span data-ttu-id="8a9a2-172">クラスを使用して、このような Hamiltonians を表す場合があり `FermionHamiltonian` ます。これは、基本的に、すべての目的のインスタンスを含むリストです `FermionTerm` 。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-172">We may represent such Hamiltonians using the `FermionHamiltonian` class, which is essentially a list containing all the desired `FermionTerm` instances.</span></span>
<span data-ttu-id="8a9a2-173">Hamiltonians が Hermitian によって定義されているため、用語 `HermitianFermionTerm` が等しいかどうかをチェックするときに Hermitian 対称も使用する、より特殊な型を使用して用語にインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-173">As Hamiltonians are Hermitian by definition, we index terms using the more specialized type `HermitianFermionTerm` that also uses Hermitian symmetry when checking whether terms are equivalent.</span></span>

<span data-ttu-id="8a9a2-174">いくつかの例を作成してみましょう。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-174">Let us construct a few illustrative examples.</span></span>
<span data-ttu-id="8a9a2-175">Hamiltonian $ \hat{H} = a_0 ^ a_1 + a_1 ^ \ ダガー a_0 $ を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-175">Consider the Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
<span data-ttu-id="8a9a2-176">Hamiltonian 演算子は Hermitian 演算子であるという事実を使用して、この構築を簡略化することがあります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-176">We may simplify this construction using the fact that Hamiltonian operators are Hermitian operators.</span></span>
<span data-ttu-id="8a9a2-177">を使用して Hamiltonian に用語を追加する場合 `Add` 、などの Hermitian 以外の用語 `fermionTerm0` は、その Hermitian 共役とペアリングされていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-177">When adding terms to the Hamiltonian using `Add`, any non-Hermitian term such as `fermionTerm0` is assumed to be paired with its Hermitian conjugate.</span></span>
<span data-ttu-id="8a9a2-178">したがって、次のスニペットも同じ Hamiltonian を表しています。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-178">Thus the following snippet also represents the same Hamiltonian:</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

<span data-ttu-id="8a9a2-179">交換規則を使用すると、Hamiltonian の一部のインスタンスは、実際には `FermionTerm` 同じシーケンスの fermionic 演算子に対応します。これは、マイナス記号の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-179">Using the anti-commutation rules, some `FermionTerm` instances in the Hamiltonian actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="8a9a2-180">たとえば、Hamiltonian $H = a_0 ^ \ ダガー a_1 ^ \ ダガー a_1 a_0-a_1 ^ \ ダガー a_0 ^ \ ダガー a_1 a_0 = 2a_0 ^ \ ダガー a_1 ^ \ ダガー a_1 a_0 $ (上記で構築した用語の合計) について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-180">For instance, consider the Hamiltonian $H=a_0^\dagger a_1^\dagger a_1 a_0 - a_1^\dagger a_0^\dagger a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, which is a sum of terms constructed above.</span></span>
<span data-ttu-id="8a9a2-181">ユーザーにとっては、これらが同等の条件であるとは限りません。そのため、Hamiltonian に個別に追加される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-181">It may not always be clear to the user that these are equivalent terms, and so they may be added to the Hamiltonian separately.</span></span>
<span data-ttu-id="8a9a2-182">または、Hamiltonian 内の既存の用語を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-182">Alternatively, one may be interested in modifying already-existing terms in the Hamiltonian.</span></span>
<span data-ttu-id="8a9a2-183">このような場合は、次のように同等の用語を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-183">In these cases, we may combine equivalent terms as follows.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
<span data-ttu-id="8a9a2-184">同等の用語の係数を組み合わせることにより、Hamiltonian 内の用語の合計数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-184">By combining coefficients of equivalent terms, we reduce the total number of terms in the Hamiltonian.</span></span>
<span data-ttu-id="8a9a2-185">後で、Hamiltonian をシミュレートするために必要なクォンタムゲートの数を減らします。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-185">Later on, this reduces the number of quantum gates required to simulate the Hamiltonian.</span></span>

### <a name="internal-representation"></a><span data-ttu-id="8a9a2-186">内部表現</span><span class="sxs-lookup"><span data-stu-id="8a9a2-186">Internal Representation</span></span>

<span data-ttu-id="8a9a2-187">1と2つの本文の相互作用を持つ fermionic Hamiltonian は、次のように2番目の量子化表記で表されます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-187">A fermionic Hamiltonian with one- and two-body interactions is represented in second-quantized notation as</span></span>

<span data-ttu-id="8a9a2-188">$ $ \begin{align} H = \ sum \_ {pq} H \_ {pq} a ^-ダガー \_ {p} a \_ {q} +-frac/ {1} {2} sum \_ {pqrs} H \_ {pqrs} a ^-ダガー \_ {p} a ^-ダガー \_ {q} a \_ {r} a \_ {s}。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-188">$$ \begin{align} H=\sum\_{pq}h\_{pq}a^\dagger\_{p}a\_{q}+\frac{1}{2}\sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}.</span></span>
<span data-ttu-id="8a9a2-189">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="8a9a2-189">\end{align} $$</span></span>

<span data-ttu-id="8a9a2-190">この表記法では、最大 $N ^ 2 + N ^ 4 $ 係数があります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-190">In this notation, there are at most $N^2+N^4$ coefficients.</span></span>
<span data-ttu-id="8a9a2-191">ただし、これらの係数の多くは、同じ演算子に対応するために収集される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-191">However, many of these coefficients may be collected as they correspond to the same operator.</span></span>
<span data-ttu-id="8a9a2-192">たとえば、$p、q、r の場合、s $ は個別のインデックスであり、交換ルールを使用して、そのことを示す場合があります: $ $ a ^ ダガー \_ {p} a ^ ダガー \_ {q} a \_ {r} a { \_ s} =-a ^ \ ダガー \_ {q} a ^-ダガー { \_ p} a \_ {r} a \_ {s} =-a ^ \ ダガー \_ {p} a ^-ダガー \_ {q} a \_ {s} a \_ {r} = a ^-ダガー \_ {q} a ^ ダガー \_ {p} a { \_ s} a \_ {r}。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-192">For instance, in the case where $p,q,r,s$ are distinct indices, we may use the anti-commutation rules to show that: $$ a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r}a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span></span>
$$

<span data-ttu-id="8a9a2-193">さらに、$H $ が Hermitian の場合、Hermitian fermionic のすべての非演算子 ($h たとえば、 \_ {pqrs} a ^ \ ダガー { \_ p} a ^ \ ダガー \_ {q} a \_ {r} a \_ {s} $ には、$H $ にもある Hermitian 共役があります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-193">Furthermore, as $H$ is Hermitian, every non-Hermitian fermionic operator, say $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, has a Hermitian conjugate that is also found in $H$.</span></span> <span data-ttu-id="8a9a2-194">これらの symmetries によって特徴付けられる用語のグループに一意にインデックスを付けるために、 \_ \_ \_ \_ 任意のシーケンスの $n + m $ fermionic operators のインデックス $ (i 1、\ cドット、i n、j 1、\ cドット $as $a、j m) $ \_ に \_ \_ \_ \_ \_ \_ 正規の \_ 順序を定義しています。これには、次のように、任意のシーケンスの任意のシーケンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-194">In order to uniquely index groups of terms characterized by these symmetries, we define a canonical ordering on the indices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ of any sequence of $n+m$ fermionic operators $a^\dagger\_{i\_1}\cdots a^\dagger\_{i\_n}a\_{j\_1}\cdots a\_{j\_m}$as follows:</span></span>
-   <span data-ttu-id="8a9a2-195">すべての作成演算子 $a ^ \ ダガー \_ {i \_ \ cdot} $ は、すべての annihilation 演算子 $a \_ {j \_ \ dot} $ の前に配置されます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-195">All creation operators $a^\dagger\_{i\_\cdot}$ are placed before all annihilation operators $a\_{j\_\cdot}$.</span></span>
-   <span data-ttu-id="8a9a2-196">すべての作成演算子のインデックスは昇順に並べ替えられます \_ 。つまり $i 1< i \_ 2</cドット < i \_ n $ になります。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-196">All creation operator indices are sorted in ascending order, that is $i\_1< i\_2< \cdots < i\_n$.</span></span>
-   <span data-ttu-id="8a9a2-197">すべての annihilation 演算子インデックスは降順に並べ替えられ、 \_ 1> j \_ 2、cドット > j \_ m $ $j ます。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-197">All annihilation operator indices are sorted in descending order, that is $j\_1> j\_2 \cdots > j\_m$.</span></span>
-   <span data-ttu-id="8a9a2-198">左端のインデックスは、右端のインデックスの値以下で、$i \_ 1 \ le j \_ m $ です。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-198">The left-most index is less than or equal to the right-most index, that is $i\_1\le j\_m$.</span></span>

<span data-ttu-id="8a9a2-199">この一連の正規の順序付けされたインデックスを $ $ \begin{align} (i \_ 1、\ cドット、i \_ n、j \_ 1、\ cドット、j m) として \_ \_ 、{n, m} で特定します。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-199">Let us identify this set of canonically ordered indices as $$ \begin{align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span></span>
<span data-ttu-id="8a9a2-200">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="8a9a2-200">\end{align} $$</span></span>

<span data-ttu-id="8a9a2-201">この標準の順序を使用すると、fermionic Hamiltonian は $ $ \begin{align} H = \ sum \_ {(p, q) \ sum {(p, q) \ In S \_ {1,1} } H ' \_ {pq} \frac{a ^ \_ /ダガー {p} a { \_ q} + a ^-ダガー { \_ q} a \_ {p}} {2} + \ sum \_ {(p, q, r, s) \ in s \_ {2,2} } H ' \_ {pqrs} \frac{a ^ \ ダガー \_ {p} a ^-ダガー { \_ q} a \_ {r} a \_ {S} + a ^-ダガー \_ {s} a ^ ダガー \_ {r} a { \_ q} a \_ {p}} {2} 、\end{align} $ $ は、適切に調整された1つの積分と2つの $h の $h を ' \_ {pq} $ と ' \_ {pqrs} $ ' としています。</span><span class="sxs-lookup"><span data-stu-id="8a9a2-201">With this canonical ordering, the fermionic Hamiltonian may be expressed as $$ \begin{align} H=\sum\_{(p,q)\in S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\dagger\_{q}a\_{p}}{2}+\sum\_{(p,q,r,s)\in S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\dagger\_{s}a^\dagger\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ with suitably adapted one- and two-electron integrals $h'\_{pq}$ and $h'\_{pqrs}$, respectively.</span></span>

