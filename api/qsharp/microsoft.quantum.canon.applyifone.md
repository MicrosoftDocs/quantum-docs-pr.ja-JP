---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: ApplyIfOne 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: 8c668423d126f02736bcb541e73e210a761c5719
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718104"
---
# <a name="applyifone-operation"></a><span data-ttu-id="9b52f-102">ApplyIfOne 操作</span><span class="sxs-lookup"><span data-stu-id="9b52f-102">ApplyIfOne operation</span></span>

<span data-ttu-id="9b52f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9b52f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9b52f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b52f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b52f-105">従来の結果値に対する条件付き操作を1として適用します。</span><span class="sxs-lookup"><span data-stu-id="9b52f-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="9b52f-106">説明</span><span class="sxs-lookup"><span data-stu-id="9b52f-106">Description</span></span>

<span data-ttu-id="9b52f-107">`op`がの場合、操作と結果の値がに適用され `result` `op` `target` `result` `One` ます。</span><span class="sxs-lookup"><span data-stu-id="9b52f-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="9b52f-108">`Zero`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="9b52f-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="9b52f-109">入力</span><span class="sxs-lookup"><span data-stu-id="9b52f-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="9b52f-110">結果: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="9b52f-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="9b52f-111">Op が適用されるかどうかを制御する測定結果。</span><span class="sxs-lookup"><span data-stu-id="9b52f-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="9b52f-112">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b52f-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9b52f-113">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="9b52f-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="9b52f-114">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="9b52f-114">target : 'T</span></span>

<span data-ttu-id="9b52f-115">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="9b52f-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b52f-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b52f-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9b52f-117">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="9b52f-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9b52f-118">&</span><span class="sxs-lookup"><span data-stu-id="9b52f-118">'T</span></span>

<span data-ttu-id="9b52f-119">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="9b52f-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b52f-120">参照</span><span class="sxs-lookup"><span data-stu-id="9b52f-120">See Also</span></span>

- [<span data-ttu-id="9b52f-121">Microsoft. Canon. Applyi(Ec)</span><span class="sxs-lookup"><span data-stu-id="9b52f-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="9b52f-122">Microsoft. Canon. Applyi(Ea)</span><span class="sxs-lookup"><span data-stu-id="9b52f-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="9b52f-123">Microsoft. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="9b52f-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)