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
# <a name="discretephaseestimationiteration-operation"></a><span data-ttu-id="48938-102">DiscretePhaseEstimationIteration 操作</span><span class="sxs-lookup"><span data-stu-id="48938-102">DiscretePhaseEstimationIteration operation</span></span>

<span data-ttu-id="48938-103">名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="48938-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="48938-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48938-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48938-105">ユニタリ oracle の整数の累乗を使用して、反復 (クラシックデプロイ制御) フェーズの推定アルゴリズムの単一の反復処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="48938-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.</span></span>

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="48938-106">入力</span><span class="sxs-lookup"><span data-stu-id="48938-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="48938-107">oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="48938-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="48938-108">整数とレジスタに作用する操作。この場合、指定されたレジスタに $U ^ m $ が適用されます。ここで $U $ は、フェーズが推定されるユニタリ、$m $ は oracle に与えられた整数乗です。</span><span class="sxs-lookup"><span data-stu-id="48938-108">Operation acting on an integer and a register, such that $U^m$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $m$ is the integer power given to the oracle</span></span>


### <a name="power--int"></a><span data-ttu-id="48938-109">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48938-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48938-110">指定されたユニタリ oracle を適用する回数。</span><span class="sxs-lookup"><span data-stu-id="48938-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="48938-111">シータ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="48938-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="48938-112">対象の状態で動作する前に、コントロール qubit のフェーズを反転する角度。</span><span class="sxs-lookup"><span data-stu-id="48938-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="48938-113">targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="48938-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="48938-114">指定されたユニタリ oracle によって操作された状態の登録。</span><span class="sxs-lookup"><span data-stu-id="48938-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="48938-115">controlQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="48938-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="48938-116">指定された oracle のアプリケーションを制御するために使用する補助 qubit。</span><span class="sxs-lookup"><span data-stu-id="48938-116">An auxiliary qubit used to control the application of the given oracle.</span></span>



## <a name="output--unit"></a><span data-ttu-id="48938-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48938-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

