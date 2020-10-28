---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721860"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="64c29-102">FixedPointReflectionPhases 関数</span><span class="sxs-lookup"><span data-stu-id="64c29-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="64c29-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="64c29-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="64c29-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64c29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64c29-105">固定小数点の振幅増幅の部分的なリフレクションフェーズを計算します。</span><span class="sxs-lookup"><span data-stu-id="64c29-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="64c29-106">入力</span><span class="sxs-lookup"><span data-stu-id="64c29-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="64c29-107">nQueries: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="64c29-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="64c29-108">状態準備 oracle に対するクエリの数。</span><span class="sxs-lookup"><span data-stu-id="64c29-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="64c29-109">は奇数の整数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="64c29-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="64c29-110">successMin: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="64c29-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="64c29-111">ターゲットの最小成功確率。</span><span class="sxs-lookup"><span data-stu-id="64c29-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="64c29-112">出力: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="64c29-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="64c29-113">固定小数点数の振幅増幅クォンタムアルゴリズムの実装で使用できるフェーズの配列。</span><span class="sxs-lookup"><span data-stu-id="64c29-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="64c29-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="64c29-114">References</span></span>

<span data-ttu-id="64c29-115">「最適な数のクエリを使用した固定ポイントの振幅増幅」のフェーズを使用します。</span><span class="sxs-lookup"><span data-stu-id="64c29-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="64c29-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) 「複合クォンタムゲートの手法」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c29-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="64c29-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) は、の形式のフェーズを `RotationPhases` 指定します。</span><span class="sxs-lookup"><span data-stu-id="64c29-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>