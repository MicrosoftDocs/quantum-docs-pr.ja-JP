---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721818"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="0214d-102">ReflectionPhases ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="0214d-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="0214d-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="0214d-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="0214d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0214d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0214d-105">振幅増幅での部分的な反射のシーケンスのフェーズ。</span><span class="sxs-lookup"><span data-stu-id="0214d-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="0214d-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="0214d-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="0214d-107">先頭: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0214d-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0214d-108">開始状態に関するリフレクションのフェーズの配列。</span><span class="sxs-lookup"><span data-stu-id="0214d-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="0214d-109">対象: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0214d-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0214d-110">対象の状態に関するリフレクションのフェーズの配列。</span><span class="sxs-lookup"><span data-stu-id="0214d-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="0214d-111">解説</span><span class="sxs-lookup"><span data-stu-id="0214d-111">Remarks</span></span>

<span data-ttu-id="0214d-112">両方の配列の長さは同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0214d-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="0214d-113">多くの場合、開始状態とターゲット状態に関する最後のフェーズに関する最初のフェーズでは、グローバルフェーズシフトが導入され、$0 $ に設定できます。</span><span class="sxs-lookup"><span data-stu-id="0214d-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>