---
uid: Microsoft.Quantum.Intrinsic.I
title: I 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 5aae7a5e3b5b441829de8f10f4df539ffc374954
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198947"
---
# <a name="i-operation"></a><span data-ttu-id="51bfc-102">I 操作</span><span class="sxs-lookup"><span data-stu-id="51bfc-102">I operation</span></span>

<span data-ttu-id="51bfc-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="51bfc-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="51bfc-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="51bfc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="51bfc-105">1つの qubit で id 操作 (no op) を実行します。</span><span class="sxs-lookup"><span data-stu-id="51bfc-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="51bfc-106">入力</span><span class="sxs-lookup"><span data-stu-id="51bfc-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="51bfc-107">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="51bfc-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="51bfc-108">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51bfc-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="51bfc-109">解説</span><span class="sxs-lookup"><span data-stu-id="51bfc-109">Remarks</span></span>

<span data-ttu-id="51bfc-110">これは、何の操作も行いません。</span><span class="sxs-lookup"><span data-stu-id="51bfc-110">This is a no-op.</span></span> <span data-ttu-id="51bfc-111">これは完全性を実現するために用意されています。また、アルゴリズムで id を呼び出したり、パラメーターとして渡したりすると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="51bfc-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>