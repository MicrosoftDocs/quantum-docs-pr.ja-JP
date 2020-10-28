---
uid: Microsoft.Quantum.Intrinsic.I
title: I 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 555f714047a38f49ccd94a77dc14a46d6f4988ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720026"
---
# <a name="i-operation"></a><span data-ttu-id="cfba6-102">I 操作</span><span class="sxs-lookup"><span data-stu-id="cfba6-102">I operation</span></span>

<span data-ttu-id="cfba6-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="cfba6-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="cfba6-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cfba6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cfba6-105">1つの qubit で id 操作 (no op) を実行します。</span><span class="sxs-lookup"><span data-stu-id="cfba6-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="cfba6-106">入力</span><span class="sxs-lookup"><span data-stu-id="cfba6-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="cfba6-107">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cfba6-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="cfba6-108">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cfba6-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cfba6-109">解説</span><span class="sxs-lookup"><span data-stu-id="cfba6-109">Remarks</span></span>

<span data-ttu-id="cfba6-110">これは、何の操作も行いません。</span><span class="sxs-lookup"><span data-stu-id="cfba6-110">This is a no-op.</span></span> <span data-ttu-id="cfba6-111">これは完全性を実現するために用意されています。また、アルゴリズムで id を呼び出したり、パラメーターとして渡したりすると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="cfba6-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>