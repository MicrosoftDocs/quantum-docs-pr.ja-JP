---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 3c0f6cf084311598346b25dd7028e290946cd87f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216287"
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

