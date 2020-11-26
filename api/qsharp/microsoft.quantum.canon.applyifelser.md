---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: ApplyIfElseR 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 874dae2ba5e842066e9c1582af431a73520e4ccd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209538"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="69045-102">ApplyIfElseR 操作</span><span class="sxs-lookup"><span data-stu-id="69045-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="69045-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="69045-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="69045-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69045-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69045-105">古典的な結果の値に応じて、2つの操作のいずれかを適用します。</span><span class="sxs-lookup"><span data-stu-id="69045-105">Applies one of two operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="69045-106">説明</span><span class="sxs-lookup"><span data-stu-id="69045-106">Description</span></span>

<span data-ttu-id="69045-107">結果が返された場合 `result` 、 `zeroOp` `zeroInput` は、がと等しいときにを入力として操作を適用し、when にを `result` 適用し `Zero` `oneOp(oneInput)` `result == One` ます。</span><span class="sxs-lookup"><span data-stu-id="69045-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="69045-108">入力</span><span class="sxs-lookup"><span data-stu-id="69045-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="69045-109">結果:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="69045-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="69045-110">またはが適用されているかどうかを判断するために使用される測定結果 `zeroOp` `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="69045-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit"></a><span data-ttu-id="69045-111">zeroOp: t => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69045-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="69045-112">に適用される操作 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="69045-112">The operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="69045-113">ゼロ入力: ' t '</span><span class="sxs-lookup"><span data-stu-id="69045-113">zeroInput : 'T</span></span>

<span data-ttu-id="69045-114">時に提供される入力 `zeroOp` `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="69045-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit"></a><span data-ttu-id="69045-115">oneOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69045-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="69045-116">に適用される操作 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="69045-116">The operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="69045-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="69045-117">oneInput : 'U</span></span>

<span data-ttu-id="69045-118">時に提供される入力 `oneOp` `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="69045-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69045-119">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69045-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="69045-120">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="69045-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="69045-121">&</span><span class="sxs-lookup"><span data-stu-id="69045-121">'T</span></span>

<span data-ttu-id="69045-122">`zeroOp`条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="69045-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="69045-123">' U</span><span class="sxs-lookup"><span data-stu-id="69045-123">'U</span></span>

<span data-ttu-id="69045-124">`oneOp`条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="69045-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="69045-125">参照</span><span class="sxs-lookup"><span data-stu-id="69045-125">See Also</span></span>

- [<span data-ttu-id="69045-126">Microsoft. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="69045-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="69045-127">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="69045-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="69045-128">Microsoft.....。</span><span class="sxs-lookup"><span data-stu-id="69045-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="69045-129">Microsoft... ".."</span><span class="sxs-lookup"><span data-stu-id="69045-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="69045-130">Microsoft. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="69045-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)