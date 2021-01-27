---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 703b50d0186cd0f4eddb9a29fa3cffb2b746c8d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843913"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="31338-102">StandardReflectionPhases 関数</span><span class="sxs-lookup"><span data-stu-id="31338-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="31338-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="31338-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="31338-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="31338-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="31338-105">標準の振幅増幅の部分的なリフレクションフェーズを計算します。</span><span class="sxs-lookup"><span data-stu-id="31338-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="31338-106">入力</span><span class="sxs-lookup"><span data-stu-id="31338-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="31338-107">nIterations: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="31338-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="31338-108">部分的なリフレクションフェーズを生成するための振幅増幅の反復回数。</span><span class="sxs-lookup"><span data-stu-id="31338-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="31338-109">出力: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="31338-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="31338-110">部分的な反射として指定されたフェーズを実装する操作</span><span class="sxs-lookup"><span data-stu-id="31338-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="31338-111">解説</span><span class="sxs-lookup"><span data-stu-id="31338-111">Remarks</span></span>

<span data-ttu-id="31338-112">すべてのフェーズは $ \ pi $ ですが、開始状態に関する最初のリフレクションとターゲット状態に関する最後のリフレクション ($0 $) は除きます。</span><span class="sxs-lookup"><span data-stu-id="31338-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>