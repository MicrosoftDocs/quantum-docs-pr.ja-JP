---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: AdiabaticStateEnergyUnitary 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: a69eb29318a750bea9c7c84ae4f90f7a31007c33
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225535"
---
# <a name="adiabaticstateenergyunitary-operation"></a>AdiabaticStateEnergyUnitary 操作

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


を使用して状態の準備を実行し、その後、を使用して `statePrepUnitary` adiabatic 状態の準備を行い `adiabaticUnitary` ます。最後に、を使用して、結果の状態に関してフェーズの推定を行い `qpeUnitary` `phaseEstAlgorithm` ます。

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a>入力

### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

初期 dynamical ジェネレーターの状態の準備を表す oracle。


### <a name="adiabaticunitary--qubit--unit"></a>adiabaticUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

アルゴリズムの最終状態にスイープを実装するために使用される adiabatic 進化アルゴリズムを表す oracle。


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a>qpeUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl

この oracle では、dynamical ジェネレーターでの時間 $ \ デルタ t $ の進化を表す $ (グランドステート $ \ket{\phi} $ およびグラウンドステートエネルギー $E = \ phi \\ , \ デルタ t $) を $U 表す oracle。


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double) 

特定のユニタリ操作に対してフェーズ推定を実行する操作。
詳細については、「 [反復フェーズの推定](/quantum/libraries/characterization#iterative-phase-estimation) 」を参照してください。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

シミュレーションを実行するために使用される qubits のレジスタ。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

$U $ によって表されるジェネレーターの地表状態エネルギー $ \ phi $ の推定 $ \hat{\phi} $。