---
uid: Microsoft.Quantum.Simulation.EstimateEnergyWithAdiabaticEvolution
title: EstimateEnergyWithAdiabaticEvolution 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergyWithAdiabaticEvolution
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: b279d35418b8f013ad0d72e9a980c9bf6ce0689a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225331"
---
# <a name="estimateenergywithadiabaticevolution-operation"></a>EstimateEnergyWithAdiabaticEvolution 操作

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


自動的に割り当てられた入力状態にを適用することによって状態の準備を実行した後、を使用して adiabatic 状態の準備を実行した後、を使用して `statePrepUnitary` `adiabaticUnitary` `qpeUnitary` 結果の状態に関する最後のフェーズ推定を実行し `phaseEstAlgorithm` ます。

```qsharp
operation EstimateEnergyWithAdiabaticEvolution (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a>入力

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

シミュレーションに使用される qubits の数。


### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

初期 dynamical ジェネレーターの状態の準備を表す oracle。


### <a name="adiabaticunitary--qubit--unit"></a>adiabaticUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

アルゴリズムの最終状態にスイープを実装するために使用される adiabatic 進化アルゴリズムを表す oracle。


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a>qpeUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl

この oracle では、dynamical ジェネレーターでの時間 $ \ デルタ t $ の進化を表す $ (グランドステート $ \ket{\phi} $ およびグラウンドステートエネルギー $E = \ phi \\ , \ デルタ t $) を $U 表す oracle。


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double) 

特定のユニタリ操作に対してフェーズ推定を実行する操作。
詳細については、「 [反復フェーズの推定](/quantum/libraries/characterization#iterative-phase-estimation) 」を参照してください。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

$U $ によって表されるジェネレーターの地表状態エネルギー $ \ phi $ の推定 $ \hat{\phi} $。