---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: ApplyIfOne 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: b7c07e01ebcaf2d475283bea0695aa68dd10776e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209402"
---
# <a name="applyifone-operation"></a><span data-ttu-id="96162-102">ApplyIfOne 操作</span><span class="sxs-lookup"><span data-stu-id="96162-102">ApplyIfOne operation</span></span>

<span data-ttu-id="96162-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="96162-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="96162-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="96162-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="96162-105">従来の結果値に対する条件付き操作を1として適用します。</span><span class="sxs-lookup"><span data-stu-id="96162-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="96162-106">説明</span><span class="sxs-lookup"><span data-stu-id="96162-106">Description</span></span>

<span data-ttu-id="96162-107">`op`がの場合、操作と結果の値がに適用され `result` `op` `target` `result` `One` ます。</span><span class="sxs-lookup"><span data-stu-id="96162-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="96162-108">`Zero`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="96162-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="96162-109">入力</span><span class="sxs-lookup"><span data-stu-id="96162-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="96162-110">結果:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="96162-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="96162-111">Op が適用されるかどうかを制御する測定結果。</span><span class="sxs-lookup"><span data-stu-id="96162-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="96162-112">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96162-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="96162-113">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="96162-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="96162-114">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="96162-114">target : 'T</span></span>

<span data-ttu-id="96162-115">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="96162-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="96162-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96162-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="96162-117">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="96162-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="96162-118">&</span><span class="sxs-lookup"><span data-stu-id="96162-118">'T</span></span>

<span data-ttu-id="96162-119">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="96162-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="96162-120">参照</span><span class="sxs-lookup"><span data-stu-id="96162-120">See Also</span></span>

- [<span data-ttu-id="96162-121">Microsoft. Canon. Applyi(Ec)</span><span class="sxs-lookup"><span data-stu-id="96162-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="96162-122">Microsoft. Canon. Applyi(Ea)</span><span class="sxs-lookup"><span data-stu-id="96162-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="96162-123">Microsoft. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="96162-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)