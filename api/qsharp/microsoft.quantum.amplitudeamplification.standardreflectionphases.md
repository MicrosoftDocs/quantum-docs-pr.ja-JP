---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721734"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="93e8f-102">StandardReflectionPhases 関数</span><span class="sxs-lookup"><span data-stu-id="93e8f-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="93e8f-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="93e8f-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="93e8f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93e8f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93e8f-105">標準の振幅増幅の部分的なリフレクションフェーズを計算します。</span><span class="sxs-lookup"><span data-stu-id="93e8f-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="93e8f-106">入力</span><span class="sxs-lookup"><span data-stu-id="93e8f-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="93e8f-107">nIterations: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="93e8f-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="93e8f-108">部分的なリフレクションフェーズを生成するための振幅増幅の反復回数。</span><span class="sxs-lookup"><span data-stu-id="93e8f-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="93e8f-109">出力: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="93e8f-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="93e8f-110">部分的な反射として指定されたフェーズを実装する操作</span><span class="sxs-lookup"><span data-stu-id="93e8f-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="93e8f-111">解説</span><span class="sxs-lookup"><span data-stu-id="93e8f-111">Remarks</span></span>

<span data-ttu-id="93e8f-112">すべてのフェーズは $ \ pi $ ですが、開始状態に関する最初のリフレクションとターゲット状態に関する最後のリフレクション ($0 $) は除きます。</span><span class="sxs-lookup"><span data-stu-id="93e8f-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>