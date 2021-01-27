---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843961"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="386bd-102">RotationPhases ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="386bd-102">RotationPhases user defined type</span></span>

<span data-ttu-id="386bd-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="386bd-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="386bd-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="386bd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="386bd-105">振幅増幅での単一 qubit 回転のシーケンスのフェーズ。</span><span class="sxs-lookup"><span data-stu-id="386bd-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="386bd-106">解説</span><span class="sxs-lookup"><span data-stu-id="386bd-106">Remarks</span></span>

<span data-ttu-id="386bd-107">1つ目のパラメーターは、反射のフェーズの配列であり、単 qubit 回転の積として表現されます。</span><span class="sxs-lookup"><span data-stu-id="386bd-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="386bd-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="386bd-108">[ G.H.</span></span> <span data-ttu-id="386bd-109">低、I. L。</span><span class="sxs-lookup"><span data-stu-id="386bd-109">Low, I. L.</span></span> <span data-ttu-id="386bd-110">語, https://arxiv.org/abs/1707.05391 ] を入力します。</span><span class="sxs-lookup"><span data-stu-id="386bd-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>