---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: 743ece778239c223573a3a8536ae8059cea09d5f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191348"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="65993-102">ReflectionPhases ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="65993-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="65993-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="65993-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="65993-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65993-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65993-105">振幅増幅での部分的な反射のシーケンスのフェーズ。</span><span class="sxs-lookup"><span data-stu-id="65993-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="65993-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="65993-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="65993-107">先頭: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="65993-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="65993-108">開始状態に関するリフレクションのフェーズの配列。</span><span class="sxs-lookup"><span data-stu-id="65993-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="65993-109">対象: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="65993-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="65993-110">対象の状態に関するリフレクションのフェーズの配列。</span><span class="sxs-lookup"><span data-stu-id="65993-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="65993-111">解説</span><span class="sxs-lookup"><span data-stu-id="65993-111">Remarks</span></span>

<span data-ttu-id="65993-112">両方の配列の長さは同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="65993-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="65993-113">多くの場合、開始状態とターゲット状態に関する最後のフェーズに関する最初のフェーズでは、グローバルフェーズシフトが導入され、$0 $ に設定できます。</span><span class="sxs-lookup"><span data-stu-id="65993-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>