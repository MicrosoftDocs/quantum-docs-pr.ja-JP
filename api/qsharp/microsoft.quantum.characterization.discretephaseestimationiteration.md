---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 167b53d7108c64d11a4f258d17e90ba78d7dd8d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715071"
---
# <a name="discretephaseestimationiteration-operation"></a>DiscretePhaseEstimationIteration 操作

名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)

パック [](https://nuget.org/packages/)


ユニタリ oracle の整数の累乗を使用して、反復 (クラシックデプロイ制御) フェーズの推定アルゴリズムの単一の反復処理を実行します。

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
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

