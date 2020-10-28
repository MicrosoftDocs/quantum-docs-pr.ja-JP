---
uid: Microsoft.Quantum.Canon.HY
title: HY 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: bc3417ff948b718be5b96513f30f3e2714b9e20c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716144"
---
# <a name="hy-operation"></a><span data-ttu-id="1d032-102">HY 操作</span><span class="sxs-lookup"><span data-stu-id="1d032-102">HY operation</span></span>

<span data-ttu-id="1d032-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1d032-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1d032-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1d032-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1d032-105">Y ベースのアナログを、Z 軸と Y 軸をインターチェンジする Hadamard 変換に適用します。</span><span class="sxs-lookup"><span data-stu-id="1d032-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="1d032-106">1つの qubit で Y Hadamard 変換 $H _Y = S H $ は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1d032-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="1d032-107">\begin{align} H_Y \mathrel{: =} \ frac {1} {\ sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i &-i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="1d032-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="1d032-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="1d032-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="1d032-109">入力</span><span class="sxs-lookup"><span data-stu-id="1d032-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="1d032-110">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1d032-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1d032-111">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="1d032-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1d032-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d032-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="1d032-113">参照</span><span class="sxs-lookup"><span data-stu-id="1d032-113">See Also</span></span>

- [<span data-ttu-id="1d032-114">Microsoft. Quantum. .H</span><span class="sxs-lookup"><span data-stu-id="1d032-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)