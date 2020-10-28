---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: a3914a4b19e3b898b6de8808699da09d386f487a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715080"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="eb6e2-102">ContinuousPhaseEstimationIteration 操作</span><span class="sxs-lookup"><span data-stu-id="eb6e2-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="eb6e2-103">名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="eb6e2-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="eb6e2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb6e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb6e2-105">ユニタリ oracle の任意の真の累乗を使用して、反復 (クラシックデプロイ制御) フェーズの推定アルゴリズムの単一の反復処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="eb6e2-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="eb6e2-106">入力</span><span class="sxs-lookup"><span data-stu-id="eb6e2-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="eb6e2-107">oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="eb6e2-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="eb6e2-108">Double $t $ とレジスタに作用する操作。この場合、指定されたレジスタに ^ t $ $U 適用されます。 $U $ は、フェーズが $t 推定されるユニタリ、$ $ は oracle に与えられた整数のべき乗です。</span><span class="sxs-lookup"><span data-stu-id="eb6e2-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="eb6e2-109">時刻: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eb6e2-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eb6e2-110">指定されたユニタリ oracle を適用する回数。</span><span class="sxs-lookup"><span data-stu-id="eb6e2-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="eb6e2-111">シータ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eb6e2-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eb6e2-112">対象の状態で動作する前に、コントロール qubit のフェーズを反転する角度。</span><span class="sxs-lookup"><span data-stu-id="eb6e2-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="eb6e2-113">targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="eb6e2-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="eb6e2-114">指定されたユニタリ oracle によって操作された状態の登録。</span><span class="sxs-lookup"><span data-stu-id="eb6e2-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="eb6e2-115">controlQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="eb6e2-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="eb6e2-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb6e2-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

