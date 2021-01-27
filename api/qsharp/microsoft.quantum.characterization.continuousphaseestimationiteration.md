---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851909"
---
# <a name="continuousphaseestimationiteration-operation"></a>ContinuousPhaseEstimationIteration 操作

名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ユニタリ oracle の任意の真の累乗を使用して、反復 (クラシックデプロイ制御) フェーズの推定アルゴリズムの単一の反復処理を実行します。

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="oracle--continuousoracle"></a>oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Double $t $ とレジスタに作用する操作。この場合、指定されたレジスタに ^ t $ $U 適用されます。 $U $ は、フェーズが $t 推定されるユニタリ、$ $ は oracle に与えられた整数のべき乗です。


### <a name="time--double"></a>時刻: [Double](xref:microsoft.quantum.lang-ref.double)

指定されたユニタリ oracle を適用する回数。


### <a name="theta--double"></a>シータ: [Double](xref:microsoft.quantum.lang-ref.double)

対象の状態で動作する前に、コントロール qubit のフェーズを反転する角度。


### <a name="targetstate--qubit"></a>targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

指定されたユニタリ oracle によって操作された状態の登録。


### <a name="controlqubit--qubit"></a>controlQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

