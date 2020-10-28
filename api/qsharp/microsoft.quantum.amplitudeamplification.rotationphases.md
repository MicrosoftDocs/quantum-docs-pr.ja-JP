---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721767"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="59450-102">RotationPhases ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="59450-102">RotationPhases user defined type</span></span>

<span data-ttu-id="59450-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="59450-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="59450-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="59450-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="59450-105">振幅増幅での単一 qubit 回転のシーケンスのフェーズ。</span><span class="sxs-lookup"><span data-stu-id="59450-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="59450-106">解説</span><span class="sxs-lookup"><span data-stu-id="59450-106">Remarks</span></span>

<span data-ttu-id="59450-107">1つ目のパラメーターは、反射のフェーズの配列であり、単 qubit 回転の積として表現されます。</span><span class="sxs-lookup"><span data-stu-id="59450-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="59450-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="59450-108">[ G.H.</span></span> <span data-ttu-id="59450-109">低、I. L。</span><span class="sxs-lookup"><span data-stu-id="59450-109">Low, I. L.</span></span> <span data-ttu-id="59450-110">語, https://arxiv.org/abs/1707.05391 ] を入力します。</span><span class="sxs-lookup"><span data-stu-id="59450-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>