---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: ApplyAmplitudeAmplification 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: be884eab70c7f72f994baf6bd7caf05769e0d5f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721930"
---
# <a name="applyamplitudeamplification-operation"></a><span data-ttu-id="b78a9-102">ApplyAmplitudeAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="b78a9-102">ApplyAmplitudeAmplification operation</span></span>

<span data-ttu-id="b78a9-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="b78a9-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="b78a9-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b78a9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b78a9-105">指定された一連のフェーズと oracles を使用して、指定されたレジスタに振幅増幅を適用し、初期状態と最終状態を反映します。</span><span class="sxs-lookup"><span data-stu-id="b78a9-105">Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.</span></span>

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b78a9-106">入力</span><span class="sxs-lookup"><span data-stu-id="b78a9-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="b78a9-107">フェーズ: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="b78a9-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="b78a9-108">振幅増幅アルゴリズムの各ステップでの部分的な反射を説明する一連のフェーズ。</span><span class="sxs-lookup"><span data-stu-id="b78a9-108">A set of phases describing the partial reflections at each step of the amplitude amplification algorithm.</span></span> <span data-ttu-id="b78a9-109">例については、「@"microsoft.quantum.amplitudeamplification.standardreflectionphases"」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b78a9-109">See @"microsoft.quantum.amplitudeamplification.standardreflectionphases" for an example.</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="b78a9-110">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="b78a9-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="b78a9-111">初期状態を反映する oracle。</span><span class="sxs-lookup"><span data-stu-id="b78a9-111">An oracle that reflects about the initial state.</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="b78a9-112">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="b78a9-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="b78a9-113">目的の最終状態を反映する oracle。</span><span class="sxs-lookup"><span data-stu-id="b78a9-113">An oracle that reflects about the desired final state.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b78a9-114">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b78a9-114">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b78a9-115">振幅増幅を実行するレジスタ。</span><span class="sxs-lookup"><span data-stu-id="b78a9-115">A register to perform amplitude amplification on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b78a9-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b78a9-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

