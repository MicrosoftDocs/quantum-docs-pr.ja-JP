---
title: エネルギー準位の推定の取得
description: 分子 hydrogen のエネルギーレベルの値を推定するサンプル Q&a プログラムについて説明します。
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 3242d8c6dc6fad2bd99055027dd7ce4ec3510ff4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276052"
---
# <a name="obtaining-energy-level-estimates"></a>エネルギー準位の推定の取得
エネルギーレベルの値の推定は、量子化学の主要なアプリケーションの1つです。 ここでは、分子 Hydrogen の正規の例に対してこれを実行する方法について説明します。 このセクションで参照されているサンプルは、 `MolecularHydrogen` 化学サンプルリポジトリにあります。 出力をプロットするより視覚的な例は `MolecularHydrogenGUI` デモです。

最初の手順は、分子 Hydrogen を表す Hamiltonian を構築することです。 これは NWChem ツールを使用して構築できますが、このサンプルでは簡潔にするために Hamiltonian 用語を手動で追加します。

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

    // We initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

Hamiltonian をシミュレートするには、演算子を qubit 演算子に変換する必要があります。 この変換は、次のように、ヨルダン-Wigner エンコーディングを使用して実行されます。

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // We also need to create an input quantum state to this Hamiltonian.
    // Let us use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

ここで、 `qSharpData` Hamiltonian dynamics をシミュレートするときに、Hamiltonian を表すを関数に渡し `TrotterStepOracle` [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms)ます。 `TrotterStepOracle`Hamiltonian のリアルタイムの進化を近似するクォンタム操作を返します。

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

これで、上記のシミュレーションを使用して、標準ライブラリのフェーズ推定アルゴリズムを使用して、グラウンドステートエネルギーを学習できるようになりました。 そのためには、クォンタムのグラウンドの状態に対して適切な概算を準備する必要があります。 このような概算の提案はスキーマに記載されています `Broombridge` が、これらの推奨事項はありません。既定のアプローチでは、最長一致に多数の原子が追加され `hamiltonian.NElectrons` ます。これにより、斜線 1-電子用語注ぎが最小化されます。 フェーズ推定関数と操作は、 [Microsoft の Quantum 名前空間](xref:microsoft.quantum.characterization in DocFX notation)にあります。

次のスニペットは、化学シミュレーションライブラリによる実際の時系列出力が、クォンタムフェーズ推定と統合されるしくみを示しています。

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined below.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // We use the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // We obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // We return both the estimated phase, and the estimated energy.
    return (estPhase, estEnergy);
}
```

この Q # コードは、ドライバープログラムから呼び出すことができるようになりました。 次の例では、完全な状態のシミュレーターを作成し、を実行して `GetEnergyByTrotterization` 、グランドステートエネルギーを取得します。

```csharp
using (var qsim = new QuantumSimulator())
{
    // We specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // We specify the step-size of the simulated time-evolution. This needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, let us run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular Hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

2つのパラメーターが返されることに注意してください。 `energyEst`は、地表のエネルギーの推定値であり、平均である必要があり `-1.137` ます。 `phaseEst`はフェーズ推定アルゴリズムによって返される未加工のフェーズであり、が大きすぎるためにエイリアスが発生したことを診断する場合に役立ち `trotterStep` ます。
