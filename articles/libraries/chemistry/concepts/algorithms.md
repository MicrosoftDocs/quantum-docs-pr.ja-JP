---
title: Hamiltonian Dynamics のシミュレーション
description: Trotter-Suzuki の数式と qubitization を使用して Hamiltonian のシミュレーションを操作する方法について説明します。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 5dad4e4a77eea99e72eb2efac52eec61ebbdb21c
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320720"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="454c3-103">Hamiltonian Dynamics のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="454c3-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="454c3-104">Hamiltonian が基本演算子の合計として表現されたら、既知の手法のホストを使用して、dynamics を基本的なゲート操作にコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="454c3-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="454c3-105">Trotter – Suzuki 数式、unitaries の線形組み合わせ、qubitization という3つの効果的なアプローチがあります。</span><span class="sxs-lookup"><span data-stu-id="454c3-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="454c3-106">以下の3つのアプローチについて説明し、Hamiltonian シミュレーションライブラリを使用してこれらのメソッドを実装する方法の具体的な Q&a 例を示します。</span><span class="sxs-lookup"><span data-stu-id="454c3-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="454c3-107">Trotter – Suzuki 数式</span><span class="sxs-lookup"><span data-stu-id="454c3-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="454c3-108">Trotter – Suzuki 数式の背後にあるアイデアは単純なものです。 Hamiltonian を簡単にシミュレートできる Hamiltonians の合計として表現し、その後、これらの単純な evolutions のシーケンスとして、全体的な進化を概算します。</span><span class="sxs-lookup"><span data-stu-id="454c3-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="454c3-109">特に、$H = \ sum_ {j = 1} ^ m H_j $ を Hamiltonian にします。</span><span class="sxs-lookup"><span data-stu-id="454c3-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="454c3-110">次に、$ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $1 $t $。この近似値のエラーはごくわずかになります。</span><span class="sxs-lookup"><span data-stu-id="454c3-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="454c3-111">$E ^ {-i H} $ が通常の指数の場合、この近似値のエラーは $O されません (m ^ 2 t ^ 2) $: 0 になります。</span><span class="sxs-lookup"><span data-stu-id="454c3-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="454c3-112">このエラーは $e ^ {-iHt} $ が演算子指数であるために発生します。結果として、この数式を使用すると、$ terms _j $H (*つまり*、$H _j H_k \n e H_k H_j $ general) ではないことが原因でエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="454c3-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute (*i.e.*, $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="454c3-113">$T $ が大きい場合でも、Trotter – Suzuki 式を使用して、短時間の一連の手順に分割することで、dynamics を正確にシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="454c3-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="454c3-114">$R $ を時間の進化に使用されるステップの数にします。そのため、各時間ステップは、$t/r $ の時間に実行されます。</span><span class="sxs-lookup"><span data-stu-id="454c3-114">Let $r$ be the number of steps taken in the time evolution, so each time step runs for time $t/r$.</span></span> <span data-ttu-id="454c3-115">次に、$ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r)、$ $ は、$ $m t ^ 2/\ イプシロン $ として $r $ のスケールを設定した場合、$-イプシロン > 0 $ に対して最大 $/イプシロン $ にエラーを加えることを意味します。</span><span class="sxs-lookup"><span data-stu-id="454c3-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="454c3-116">エラー条件がキャンセルされるように、一連の演算子指数を構築することで、より正確な概数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="454c3-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="454c3-117">このような最も単純な数式では、2番目の order Trotter Suzuki 式です。 $ $ U_2 (t) = \ left (\ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2r} \ prod_ {j = m} の形式で取得します ^ 1 e ^ {-iH_j t/2r} \ right) ^ r = e ^ {-iht} + O (m ^ 3 t ^ 3/r ^ 2)、$ $ {3/2} t ^ {3/2}//sqrt {\ イプシロン} $ としてスケールする $r $ を選択すると、$-イプシロン > 0 $ の $-イプシロン $ よりも小さくすることができます。 $m</span><span class="sxs-lookup"><span data-stu-id="454c3-117">The simplest such formula, the second order Trotter-Suzuki formula, takes the form $$ U_2(t) = \left(\prod_{j=1}^{m} e^{-iH_j t/2r} \prod_{j=m}^1 e^{-iH_j t/2r}\right)^r = e^{-iHt} + O(m^3 t^3/r^2), $$ the error of which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="454c3-118">さらに上位の数式でも、特に ($ 2k $) $k > 0 $ の順序は、次のように再帰的に構築できます。 $ $ U_ {2k} (t) = [U_ {2k-2} (s_k\~ t)] ^ 2 U_ {2k-2} ([1-4s_k] t) [U_ {2k-2} (s_k\~ t)] ^ 2 = e ^ {-iHt} + O ((m t) ^ {2k + 1}/r ^ {2k})、$ $ where $s _k = (4-4 ^ {1/(2k-1)}) ^{-1}$。</span><span class="sxs-lookup"><span data-stu-id="454c3-118">Even higher-order formulas, specifically ($2k$)th-order for $k>0$, can be constructed recursively: $$ U_{2k}(t) = [U_{2k-2}(s_k\~ t)]^2 U_{2k-2}([1-4s_k]t) [U_{2k-2}(s_k\~ t)]^2 = e^{-iHt} + O((m t)^{2k+1}/r^{2k}), $$ where $s_k = (4-4^{1/(2k-1)})^{-1}$.</span></span>

<span data-ttu-id="454c3-119">最も単純なのは、次の4番目の順序 ($k = $2) の数式です。最初に Suzuki: $ $ U_4 (t) = [U_2 (s_2\~ t)] ^ 2 U_2 ([1-4s_2] t) [U_2 (s_2\~ t)] ^ 2 = e ^ {-iHt} + O (m ^ 5t ^ 5/$ $ where $s _2 = (4-4 ^ {1/3}) ^{-1}$。</span><span class="sxs-lookup"><span data-stu-id="454c3-119">The simplest is the following fourth order ($k=2$) formula, originally introduced by Suzuki: $$ U_4(t) = [U_2(s_2\~ t)]^2 U_2([1-4s_2]t) [U_2(s_2\~ t)]^2 = e^{-iHt} +O(m^5t^5/r^4), $$ where $s_2 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="454c3-120">一般に、任意の上位の数式を同様に構築できます。ただし、多くの場合、より複雑なインテグレーターを使用することによって生じるコストは、最も現実的な問題の4番目の順序を超える利点を上回ることになります。</span><span class="sxs-lookup"><span data-stu-id="454c3-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="454c3-121">上記の戦略を機能させるためには、$e ^ {-iH_j t} $ の幅広いクラスをシミュレートするためのメソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="454c3-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="454c3-122">ここで使用できる最も単純な Hamiltonians のファミリは、Pare Li 演算子です。</span><span class="sxs-lookup"><span data-stu-id="454c3-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="454c3-123">Diagonalized 演算子は、Clifford 操作 (クォンタムコンピューティングの標準ゲート) を使用して実行できるため、簡単にシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="454c3-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="454c3-124">さらに、これらの値が diagonalized されると、それらが作用する qubits のパリティを計算することで、それらの値を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="454c3-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="454c3-125">たとえば、$ $ e ^ {-Ix\ otimes X t} = (hotimes H) e ^ {-Iz\ otimes Z t} (hotimes H), $ $ where $ $ e ^ {-i Z/otimes Z t} = \begin{bmatrix} e ^ {-it &} は 0 & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="454c3-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="454c3-126">0 & e ^ {i t} & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="454c3-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="454c3-127">0 & 0 & e ^ {it} & 0 </span><span class="sxs-lookup"><span data-stu-id="454c3-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="454c3-128">0 & 0 & 0 & e ^ {-it} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="454c3-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="454c3-129">$ $ ここ、$e ^ {-iHt} \ket{00} = e ^ {it} \ket{00}$ and $e ^ {-iHt} \ket{01} = e ^ {-it} \ket{01}$。これは、$0 $ のパリティが $0 $ で、ビット文字列 $1 $ のパリティは $1 $ であるという事実の結果として直接確認できます。</span><span class="sxs-lookup"><span data-stu-id="454c3-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="454c3-130">指数操作を使用して <xref:microsoft.quantum.intrinsic.exp>、Q # に直接実装できる p Li 演算子は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="454c3-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:microsoft.quantum.intrinsic.exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="454c3-131">Fermionic Hamiltonians の場合、[ヨルダン– Wigner 分解](xref:microsoft.quantum.chemistry.concepts.jordanwigner)は、Hamiltonian を p li 演算子の合計に簡単にマップします。</span><span class="sxs-lookup"><span data-stu-id="454c3-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="454c3-132">これは、化学をシミュレートするために、上記のアプローチを簡単に調整できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="454c3-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="454c3-133">次に、このようなシミュレーションを化学内で実行する方法の例を、以下に示します。この例では、このようなシミュレーションを実行する方法を簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="454c3-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how executing such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="454c3-134">開始点は、コードで `JordanWignerEncoding` クラスのインスタンスとして表現された、Fermionic Hamiltonian の[ヨルダンの Wigner エンコード](xref:microsoft.quantum.chemistry.concepts.jordanwigner)です。</span><span class="sxs-lookup"><span data-stu-id="454c3-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

<span data-ttu-id="454c3-135">この形式では、Q # のシミュレーションアルゴリズムで利用できるヨルダンの形式は、ユーザー定義型 `JordanWignerEncodingData`です。</span><span class="sxs-lookup"><span data-stu-id="454c3-135">This format of the Jordan–Wigner representation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="454c3-136">Q # では、この形式は便利な `TrotterStepOracle` 関数に渡されます。これは、Trotter-Suzuki インテグレーターを使用して、その実行に必要なその他のパラメーターに加えて、時間の短縮度を表す演算子を返します。</span><span class="sxs-lookup"><span data-stu-id="454c3-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="454c3-137">重要なのは、この実装では、[クォンタムコンピューターを使用した電子構造 Hamiltonians のシミュレーション](https://arxiv.org/abs/1001.3855)で説明されているいくつかの最適化を適用し、必要なシングル qubit 回転数を最小限に抑えるためにクォンタム[化学のクォンタムアルゴリズムを改善](https://arxiv.org/abs/1403.1539)し、シミュレーションエラーを減らします。</span><span class="sxs-lookup"><span data-stu-id="454c3-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="454c3-138">Qubitization</span><span class="sxs-lookup"><span data-stu-id="454c3-138">Qubitization</span></span>

<span data-ttu-id="454c3-139">Qubitization は、クォンタムウォークからのアイデアを使用して量子力学をシミュレートする、シミュレーションの代替アプローチです。</span><span class="sxs-lookup"><span data-stu-id="454c3-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="454c3-140">Qubitization は Trotter 数式よりも多くの qubits を必要としますが、メソッドは、進化時間と誤差許容範囲に応じて最適なスケーリングを保証します。</span><span class="sxs-lookup"><span data-stu-id="454c3-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="454c3-141">このような理由から、一般的な Hamiltonian dynamics をシミュレートし、特に電子構造の問題を解決するためには、この方法が好まれる方法になりました。</span><span class="sxs-lookup"><span data-stu-id="454c3-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="454c3-142">大まかに言えば、qubitization は次の手順に従ってこれを実現します。</span><span class="sxs-lookup"><span data-stu-id="454c3-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="454c3-143">1つ目は、$H = \ sum_j h_j H_j、および $H _j $ および $h _j $0 です。</span><span class="sxs-lookup"><span data-stu-id="454c3-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="454c3-144">Qubitization は、1対の反射を実行することで、$ $W = e ^ {\ pm i \ cos ^{-1}(H/| h | _1)}、$ $ where $ | H | _1 = \ sum_j | h_j | $ と同等の演算子を実装します。</span><span class="sxs-lookup"><span data-stu-id="454c3-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="454c3-145">次の手順では、ウォーク演算子の固有値を $e ^ {i\ pm \ cos ^{-1}(E_k/| h | _1)} $ から変換します。ここで $E _k $ は $H $ の固有値 $e ^ {-iE_k t} $ です。</span><span class="sxs-lookup"><span data-stu-id="454c3-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="454c3-146">これは、クォンタムの[シグナル処理](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)など、さまざまなクォンタムの単数値の変換方法を使用して実現できます。</span><span class="sxs-lookup"><span data-stu-id="454c3-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="454c3-147">または、静的な数量のみが必要な場合 (Hamiltonian の接地エネルギーなど)、その結果のコサインを取得することにより、$W $ に直接[位相推定](xref:microsoft.quantum.libraries.characterization)を適用して、結果からの地表エネルギーを推定することができます。</span><span class="sxs-lookup"><span data-stu-id="454c3-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="454c3-148">これは、クォンタムの単数値の変換方法を使用するのではなく、クラシックデプロイによってスペクトル変換を実行できるため、重要です。</span><span class="sxs-lookup"><span data-stu-id="454c3-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="454c3-149">より詳細なレベルでは、qubitization の実装には、Hamiltonian のインターフェイスを提供する2つのサブルーチンが必要です。</span><span class="sxs-lookup"><span data-stu-id="454c3-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="454c3-150">Trotter – Suzuki メソッドとは異なり、これらのサブルーチンは古典的なクォンタムではなく、実装では、Trotter ベースのシミュレーションに必要とされるよりも大きな対数ビットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="454c3-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="454c3-151">Qubitization で使用される最初のクォンタムサブルーチンは $ \ 演算子 name{select} $ という名前で、\ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \ end{} を生成することが想定されています。ここで、各 $H _j $ は Hermitian と想定されています。およびユニタリ。</span><span class="sxs-lookup"><span data-stu-id="454c3-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="454c3-152">これは制限されているように思えるかもしれませんが、PHermitian の演算子は、そのようなものであることを思い出してください。そのため、量子化学シミュレーションなどのアプリケーションは、このフレームワークに自然に分類されます。</span><span class="sxs-lookup"><span data-stu-id="454c3-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="454c3-153">$ 演算子は、実際には実際にはリフレクション操作であることがあります。</span><span class="sxs-lookup"><span data-stu-id="454c3-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="454c3-154">これは、$ k {j} \ket{\psi} = \ket{j} \ket{\psi} $ という事実から見ることができます。これは、各 $H _j $ がユニタリおよび Hermitian であり、そのために固有値 $ pm $1 があるためです。</span><span class="sxs-lookup"><span data-stu-id="454c3-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="454c3-155">2番目のサブルーチンは、$ & によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="454c3-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="454c3-156">Select 操作では、各 Hamiltonian terms _j $H にアクセスする手段が提供されていますが、prepare サブルーチンでは $h 係数にアクセスするためのメソッドが用意されています。 _j $,-begin{} \operatorname{Prepare}\ket{0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="454c3-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="454c3-157">次に、乗算制御されたフェーズゲートを使用することによって、$ $ \Lambda\ket{0}^ {/otimes n} = \begin{cases} \-\ket{x} &、} x = 0 \\があることがわかります </span><span class="sxs-lookup"><span data-stu-id="454c3-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\
        <span data-ttu-id="454c3-158">\ket{x} & \text{otherwise} \end{cases}.</span><span class="sxs-lookup"><span data-stu-id="454c3-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="454c3-159">$ & Qubitization} $ 操作は、直接には使用されません。しかし、$-\begin{align} R &amp; = 1-2 \ 演算子名 {Prepare} \ket{0}\bra{0}、\\\\ = \ オペレーター名 {} ^ &amp; を作成する状態{-1} に関するリフレクションを実装するために使用されますが、このような場合はを使用します。{-1}</span><span class="sxs-lookup"><span data-stu-id="454c3-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="454c3-160">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="454c3-160">\end{align} $$</span></span>

<span data-ttu-id="454c3-161">ウォーク演算子 $W $ は、$ & operator name{select} $ および $R $ operation as $ $ W = \ operator name{select} R, $ $ として表すことができます。これにより、同じ (アイソメトリック) と $e 同等の演算子を実装することができます。これは、^ {/pm i-cos ^{-1}(H/| H | _1)</span><span class="sxs-lookup"><span data-stu-id="454c3-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="454c3-162">これらのサブルーチンは、Q # で簡単に設定できます。</span><span class="sxs-lookup"><span data-stu-id="454c3-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="454c3-163">例として、$H = X_1 + X_2 + Z_1 Z_2 $ という単純な qubit の横形式の Hamiltonian を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="454c3-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="454c3-164">この場合、$ 演算子を実装する Q # コードは <xref:microsoft.quantum.canon.multiplexoperations>によって呼び出されます。一方、$-演算子名は、<xref:microsoft.quantum.preparation.preparearbitrarystate>を使用して実装できます。</span><span class="sxs-lookup"><span data-stu-id="454c3-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:microsoft.quantum.canon.multiplexoperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span></span>
<span data-ttu-id="454c3-165">このモデルをシミュレートする例については、 [Q # のサンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="454c3-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).</span></span>

<span data-ttu-id="454c3-166">任意の化学の問題に対してこれらの手順を手動で指定すると、多くの労力が必要になります。これは、化学ライブラリを使用しても回避できます。</span><span class="sxs-lookup"><span data-stu-id="454c3-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="454c3-167">上記の Trotter – Suzuki シミュレーションアルゴリズムと同様に、`JordanWignerEncodingData` は、実行に必要なその他のパラメーターに加えて、ウォーク演算子を返す便利な関数 `QubitizationOracle` に渡されます。</span><span class="sxs-lookup"><span data-stu-id="454c3-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="454c3-168">重要なの実装 <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> は、PHamiltonians Li 文字列の線形組み合わせとして指定された任意のに適用されます。</span><span class="sxs-lookup"><span data-stu-id="454c3-168">Importantly, the implementation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="454c3-169">化学シミュレーション用に最適化されたバージョンは <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>を使用して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="454c3-169">A version optimized for chemistry simulations is invoked using <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span></span>
<span data-ttu-id="454c3-170">このバージョンは、「[量子回線での電子 Spectra のエンコード](https://arxiv.org/abs/1805.03662)」で説明されている手法を使用した t ゲートの数を最小限に抑えるために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="454c3-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
