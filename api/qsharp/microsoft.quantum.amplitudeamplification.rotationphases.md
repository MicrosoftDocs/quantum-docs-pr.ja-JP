---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191365"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="d6b44-102">RotationPhases ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="d6b44-102">RotationPhases user defined type</span></span>

<span data-ttu-id="d6b44-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d6b44-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d6b44-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d6b44-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d6b44-105">振幅増幅での単一 qubit 回転のシーケンスのフェーズ。</span><span class="sxs-lookup"><span data-stu-id="d6b44-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="d6b44-106">解説</span><span class="sxs-lookup"><span data-stu-id="d6b44-106">Remarks</span></span>

<span data-ttu-id="d6b44-107">1つ目のパラメーターは、反射のフェーズの配列であり、単 qubit 回転の積として表現されます。</span><span class="sxs-lookup"><span data-stu-id="d6b44-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="d6b44-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="d6b44-108">[ G.H.</span></span> <span data-ttu-id="d6b44-109">低、I. L。</span><span class="sxs-lookup"><span data-stu-id="d6b44-109">Low, I. L.</span></span> <span data-ttu-id="d6b44-110">語, https://arxiv.org/abs/1707.05391 ] を入力します。</span><span class="sxs-lookup"><span data-stu-id="d6b44-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>