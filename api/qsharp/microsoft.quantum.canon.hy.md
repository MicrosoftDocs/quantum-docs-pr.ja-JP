---
uid: Microsoft.Quantum.Canon.HY
title: HY 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: 119d78c4cd8d5e5d92cb54ff652b082a1b99ae06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840443"
---
# <a name="hy-operation"></a><span data-ttu-id="94bef-102">HY 操作</span><span class="sxs-lookup"><span data-stu-id="94bef-102">HY operation</span></span>

<span data-ttu-id="94bef-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="94bef-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="94bef-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94bef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94bef-105">Y ベースのアナログを、Z 軸と Y 軸をインターチェンジする Hadamard 変換に適用します。</span><span class="sxs-lookup"><span data-stu-id="94bef-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="94bef-106">1つの qubit で Y Hadamard 変換 $H _Y = S H $ は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="94bef-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="94bef-107">\begin{align} H_Y \mathrel{: =} \ frac {1} {\ sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i &-i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="94bef-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="94bef-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="94bef-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="94bef-109">入力</span><span class="sxs-lookup"><span data-stu-id="94bef-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="94bef-110">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="94bef-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="94bef-111">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="94bef-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="94bef-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94bef-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="94bef-113">参照</span><span class="sxs-lookup"><span data-stu-id="94bef-113">See Also</span></span>

- [<span data-ttu-id="94bef-114">Microsoft. Quantum. .H</span><span class="sxs-lookup"><span data-stu-id="94bef-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)