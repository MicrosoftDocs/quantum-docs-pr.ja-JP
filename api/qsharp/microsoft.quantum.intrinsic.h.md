---
uid: Microsoft.Quantum.Intrinsic.H
title: H 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: H
qsharp.summary: >-
  Applies the Hadamard transformation to a single qubit.

  \begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}. \end{align}
ms.openlocfilehash: 6f02390588c9de38f69802575429aff749f70ac5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212377"
---
# <a name="h-operation"></a><span data-ttu-id="66285-102">H 操作</span><span class="sxs-lookup"><span data-stu-id="66285-102">H operation</span></span>

<span data-ttu-id="66285-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="66285-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="66285-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="66285-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="66285-105">Hadamard 変換を1つの qubit に適用します。</span><span class="sxs-lookup"><span data-stu-id="66285-105">Applies the Hadamard transformation to a single qubit.</span></span>

<span data-ttu-id="66285-106">\begin{align} H \mathrel{: =} \ frac {1} {\ sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ 1 &-1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="66285-106">\begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="66285-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="66285-107">\end{align}</span></span>

```qsharp
operation H (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="66285-108">入力</span><span class="sxs-lookup"><span data-stu-id="66285-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="66285-109">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="66285-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="66285-110">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="66285-110">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="66285-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="66285-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

