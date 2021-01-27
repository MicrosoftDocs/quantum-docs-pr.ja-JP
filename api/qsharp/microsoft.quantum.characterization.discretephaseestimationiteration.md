---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 03e2300dcc2d2cb42992e074833c8cd2530e898b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839970"
---
# <a name="discretephaseestimationiteration-operation"></a>DiscretePhaseEstimationIteration 操作

名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ユニタリ oracle の整数の累乗を使用して、反復 (クラシックデプロイ制御) フェーズの推定アルゴリズムの単一の反復処理を実行します。

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="oracle--discreteoracle"></a>oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

整数とレジスタに作用する操作。この場合、指定されたレジスタに $U ^ m $ が適用されます。ここで $U $ は、フェーズが推定されるユニタリ、$m $ は oracle に与えられた整数乗です。


### <a name="power--int"></a>power: [Int](xref:microsoft.quantum.lang-ref.int)

指定されたユニタリ oracle を適用する回数。


### <a name="theta--double"></a>シータ: [Double](xref:microsoft.quantum.lang-ref.double)

対象の状態で動作する前に、コントロール qubit のフェーズを反転する角度。


### <a name="targetstate--qubit"></a>targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

指定されたユニタリ oracle によって操作された状態の登録。


### <a name="controlqubit--qubit"></a>controlQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

指定された oracle のアプリケーションを制御するために使用する補助 qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

