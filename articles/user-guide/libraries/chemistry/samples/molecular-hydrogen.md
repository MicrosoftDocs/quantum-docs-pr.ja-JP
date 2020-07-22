---
title: エネルギー準位の推定の取得
description: 分子 hydrogen のエネルギーレベルの値を推定するサンプル Q&a プログラムについて説明します。
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: b26538980366cf4cbe01fc2ef59580ae182f1e8a
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871570"
---
# <a name="obtaining-energy-level-estimates"></a>エネルギー準位の推定の取得
エネルギーレベルの値の推定は、量子化学の主要なアプリケーションの1つです。 この記事では、分子 hydrogen の正規の例に対してこれを実行する方法について説明します。 このセクションで参照されているサンプルは、 [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) 化学サンプルリポジトリにあります。 出力をプロットするより視覚的な例は [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogenGUI) デモです。

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a>分子 hydrogen のエネルギー値の推定

最初の手順では、分子 hydrogen を表す Hamiltonian を構築します。 これは NWChem ツールを使用して構築できますが、簡潔にするために、このサンプルでは Hamiltonian 用語を手動で追加します。

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

Hamiltonian をシミュレートするには、演算子を qubit 演算子に変換する必要があります。 この変換は、次のように、ヨルダン-Wigner エンコードを使用して実行されます。

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

次に、 `qSharpData` Hamiltonian を表すを関数に渡し `TrotterStepOracle` ます。 `TrotterStepOracle`Hamiltonian のリアルタイムの進化を近似するクォンタム操作を返します。 詳細については、「 [Hamiltonian dynamics のシミュレーション](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms)」を参照してください。

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

この時点で、標準ライブラリの[フェーズ推定アルゴリズム](xref:microsoft.quantum.libraries.characterization)を使用して、前のシミュレーションを使用して、グラウンドの状態エネルギーを学習できます。 そのためには、クォンタムのグラウンドの状態に対して適切な概算を準備する必要があります。 このような概算の提案は、スキーマに記載されてい [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) ます。 ただし、これらの推奨事項を省略すると、既定の方法では、最長一致に多数の原子が追加され `hamiltonian.NElectrons` ます。これにより、対角線の 1 ~ 3 の注ぎが最小化されます。 フェーズの推定関数と操作は、DocFX 表記で[、名前空間](xref:microsoft.quantum.characterization)に用意されています。

次のスニペットは、化学シミュレーションライブラリによるリアルタイムの進化の出力を、クォンタムフェーズ推定と統合する方法を示しています。

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

これで、ホストプログラムから Q # コードを呼び出すことができます。 次の C# コードは、完全な状態のシミュレーターを作成し、を実行して `GetEnergyByTrotterization` 、グラウンドステートエネルギーを取得します。

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

操作は、次の2つのパラメーターを返します。 

- `energyEst`は、地表のエネルギーの推定値であり、平均に近い状態になる必要があり `-1.137` ます。 
- `phaseEst`フェーズ推定アルゴリズムによって返される未加工のフェーズです。 これは、値が大きすぎるためにエイリアスが発生した場合に、エイリアスを診断するのに役立ち `trotterStep` ます。
