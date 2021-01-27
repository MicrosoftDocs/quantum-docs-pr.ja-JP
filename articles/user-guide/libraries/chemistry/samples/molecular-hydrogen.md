---
title: エネルギー準位の推定の取得
description: Q#分子 hydrogen のエネルギーレベルの値を推定するサンプルプログラムについて説明します。
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: sample
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- Q#
- $$v
ms.openlocfilehash: 60935e7c1e8c674fab3a546c1f110f589d2e6b77
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855056"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="b8f26-103">エネルギー準位の推定の取得</span><span class="sxs-lookup"><span data-stu-id="b8f26-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="b8f26-104">エネルギーレベルの値の推定は、量子化学の主要なアプリケーションの1つです。</span><span class="sxs-lookup"><span data-stu-id="b8f26-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="b8f26-105">この記事では、分子 hydrogen の正規の例に対してこれを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8f26-105">This article outlines how you can perform this for the canonical example of molecular hydrogen.</span></span> <span data-ttu-id="b8f26-106">このセクションで参照されているサンプルは、 [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) 化学サンプルリポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="b8f26-106">The sample referenced in this section is [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) in the chemistry samples repository.</span></span> <span data-ttu-id="b8f26-107">出力をプロットするより視覚的な例は [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) デモです。</span><span class="sxs-lookup"><span data-stu-id="b8f26-107">A more visual example that plots the output is the [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demo.</span></span>

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a><span data-ttu-id="b8f26-108">分子 hydrogen のエネルギー値の推定</span><span class="sxs-lookup"><span data-stu-id="b8f26-108">Estimating the energy values of molecular hydrogen</span></span>

<span data-ttu-id="b8f26-109">最初の手順では、分子 hydrogen を表す Hamiltonian を構築します。</span><span class="sxs-lookup"><span data-stu-id="b8f26-109">The first step is to construct the Hamiltonian representing molecular hydrogen.</span></span> <span data-ttu-id="b8f26-110">これは NWChem ツールを使用して構築できますが、簡潔にするために、このサンプルでは Hamiltonian 用語を手動で追加します。</span><span class="sxs-lookup"><span data-stu-id="b8f26-110">Although you can construct this using the NWChem tool, for brevity, this sample adds the Hamiltonian terms manually.</span></span>

```csharp
    // These orbital integrals are represented using the OrbitalIntegral
    // data structure.
    var energyOffset = 0.713776188; // This is the coulomb repulsion
    var nElectrons = 2; // Molecular hydrogen has two electrons
    var orbitalIntegrals = new OrbitalIntegral[]
    {
        new OrbitalIntegral(new[] { 0,0 }, -1.252477495),
        new OrbitalIntegral(new[] { 1,1 }, -0.475934275),
        new OrbitalIntegral(new[] { 0,0,0,0 }, 0.674493166),
        new OrbitalIntegral(new[] { 0,1,0,1 }, 0.181287518),
        new OrbitalIntegral(new[] { 0,1,1,0 }, 0.663472101),
        new OrbitalIntegral(new[] { 1,1,1,1 }, 0.697398010),
        // This line adds the identity term.
        new OrbitalIntegral(new int[] { }, energyOffset)
    };

    // Initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

<span data-ttu-id="b8f26-111">Hamiltonian をシミュレートするには、演算子を qubit 演算子に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8f26-111">Simulating the Hamiltonian requires converting the fermion operators to qubit operators.</span></span> <span data-ttu-id="b8f26-112">この変換は、次のように Jordan-Wigner エンコードを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="b8f26-112">This conversion is performed through the Jordan-Wigner encoding as follows:</span></span>

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // You also need to create an input quantum state to this Hamiltonian.
    // Use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

<span data-ttu-id="b8f26-113">次に、 `qSharpData` Hamiltonian を表すを関数に渡し `TrotterStepOracle` ます。</span><span class="sxs-lookup"><span data-stu-id="b8f26-113">Next, pass `qSharpData`, which represents the Hamiltonian, to the `TrotterStepOracle` function.</span></span> <span data-ttu-id="b8f26-114">`TrotterStepOracle` Hamiltonian のリアルタイムの進化を近似するクォンタム操作を返します。</span><span class="sxs-lookup"><span data-stu-id="b8f26-114">`TrotterStepOracle` returns a quantum operation that approximates the real-time evolution of the Hamiltonian.</span></span> <span data-ttu-id="b8f26-115">詳細については、「 [Hamiltonian dynamics のシミュレーション](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8f26-115">For more information, see [Simulating Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span></span>

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
```

<span data-ttu-id="b8f26-116">この時点で、標準ライブラリの [フェーズ推定アルゴリズム](xref:microsoft.quantum.libraries.characterization) を使用して、前のシミュレーションを使用して、グラウンドの状態エネルギーを学習できます。</span><span class="sxs-lookup"><span data-stu-id="b8f26-116">At this point, you can use the standard library's [phase estimation algorithms](xref:microsoft.quantum.libraries.characterization) to learn the ground state energy using the previous simulation.</span></span> <span data-ttu-id="b8f26-117">そのためには、クォンタムのグラウンドの状態に対して適切な概算を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8f26-117">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="b8f26-118">このような概算の提案は、スキーマに記載されてい [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) ます。</span><span class="sxs-lookup"><span data-stu-id="b8f26-118">Suggestions for such approximations are provided in the [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema.</span></span> <span data-ttu-id="b8f26-119">ただし、これらの推奨事項を省略すると、既定の方法では、最長一致に多数の原子が追加され `hamiltonian.NElectrons` ます。これにより、対角線の 1 ~ 3 の注ぎが最小化されます。</span><span class="sxs-lookup"><span data-stu-id="b8f26-119">However, absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="b8f26-120">フェーズの推定関数と操作は、DocFX 表記で [、名前空間](xref:Microsoft.Quantum.Characterization) に用意されています。</span><span class="sxs-lookup"><span data-stu-id="b8f26-120">The phase estimation functions and operations are provided in DocFX notation in the [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization) namespace.</span></span>

<span data-ttu-id="b8f26-121">次のスニペットは、化学シミュレーションライブラリによるリアルタイムの進化の出力を、クォンタムフェーズ推定と統合する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b8f26-121">The following snippet shows how the real-time evolution output by the chemistry simulation library integrates with quantum phase estimation.</span></span>

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // Using a Product formula, also known as `Trotterization`, to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined here.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // Using the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // Now, obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // Return both the estimated phase and the estimated energy.
    return (estPhase, estEnergy);
}
```

<span data-ttu-id="b8f26-122">これで、ホストプログラムからコードを呼び出すことができ Q# ます。</span><span class="sxs-lookup"><span data-stu-id="b8f26-122">You can now invoke the Q# code from the host program.</span></span> <span data-ttu-id="b8f26-123">次の C# コードは、完全な状態のシミュレーターを作成し、を実行して `GetEnergyByTrotterization` 、グラウンドステートエネルギーを取得します。</span><span class="sxs-lookup"><span data-stu-id="b8f26-123">The following C# code creates a full-state simulator and runs `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

```csharp
using (var qsim = new QuantumSimulator())
{
    // Specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // Specify the step size of the simulated time evolution. The step size needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

<span data-ttu-id="b8f26-124">操作は、次の2つのパラメーターを返します。</span><span class="sxs-lookup"><span data-stu-id="b8f26-124">The operation returns two parameters:</span></span> 

- <span data-ttu-id="b8f26-125">`energyEst` は、地表のエネルギーの推定値であり、平均に近い状態になる必要があり `-1.137` ます。</span><span class="sxs-lookup"><span data-stu-id="b8f26-125">`energyEst` is the estimate of the ground state energy and should be close to `-1.137` on average.</span></span> 
- <span data-ttu-id="b8f26-126">`phaseEst` フェーズ推定アルゴリズムによって返される未加工のフェーズです。</span><span class="sxs-lookup"><span data-stu-id="b8f26-126">`phaseEst` is the raw phase returned by the phase estimation algorithm.</span></span> <span data-ttu-id="b8f26-127">これは、値が大きすぎるためにエイリアスが発生した場合に、エイリアスを診断するのに役立ち `trotterStep` ます。</span><span class="sxs-lookup"><span data-stu-id="b8f26-127">This useful for diagnosing aliasing when it occurs due to a `trotterStep` value that is too large.</span></span>
