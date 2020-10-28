---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: ApplyIfZero 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 7435150937143a8d1a67afe334b683932a9655de
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718062"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="49be8-102">ApplyIfZero 操作</span><span class="sxs-lookup"><span data-stu-id="49be8-102">ApplyIfZero operation</span></span>

<span data-ttu-id="49be8-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="49be8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="49be8-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="49be8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="49be8-105">従来の結果値に対する条件付き操作を0に適用します。</span><span class="sxs-lookup"><span data-stu-id="49be8-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="49be8-106">説明</span><span class="sxs-lookup"><span data-stu-id="49be8-106">Description</span></span>

<span data-ttu-id="49be8-107">`op`がの場合、操作と結果の値がに適用され `result` `op` `target` `result` `Zero` ます。</span><span class="sxs-lookup"><span data-stu-id="49be8-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="49be8-108">`One`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="49be8-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="49be8-109">入力</span><span class="sxs-lookup"><span data-stu-id="49be8-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="49be8-110">結果: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="49be8-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="49be8-111">Op が適用されるかどうかを制御する測定結果。</span><span class="sxs-lookup"><span data-stu-id="49be8-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="49be8-112">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49be8-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="49be8-113">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="49be8-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="49be8-114">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="49be8-114">target : 'T</span></span>

<span data-ttu-id="49be8-115">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="49be8-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="49be8-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49be8-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="49be8-117">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="49be8-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="49be8-118">&</span><span class="sxs-lookup"><span data-stu-id="49be8-118">'T</span></span>

<span data-ttu-id="49be8-119">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="49be8-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="49be8-120">参照</span><span class="sxs-lookup"><span data-stu-id="49be8-120">See Also</span></span>

- [<span data-ttu-id="49be8-121">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="49be8-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="49be8-122">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="49be8-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="49be8-123">Microsoft. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="49be8-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)