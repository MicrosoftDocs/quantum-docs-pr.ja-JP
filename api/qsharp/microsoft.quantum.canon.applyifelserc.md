---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: ApplyIfElseRC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: 45bd0f46fb2e28c5c9aaa21cb7ec065baf279d2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718118"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="3724c-102">ApplyIfElseRC 操作</span><span class="sxs-lookup"><span data-stu-id="3724c-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="3724c-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3724c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3724c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3724c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3724c-105">クラシック結果の値に応じて、制御可能な2つの操作のいずれかを適用します。</span><span class="sxs-lookup"><span data-stu-id="3724c-105">Applies one of two controllable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="3724c-106">説明</span><span class="sxs-lookup"><span data-stu-id="3724c-106">Description</span></span>

<span data-ttu-id="3724c-107">結果が返された場合 `result` 、 `zeroOp` `zeroInput` は、がと等しいときにを入力として操作を適用し、when にを `result` 適用し `Zero` `oneOp(oneInput)` `result == One` ます。</span><span class="sxs-lookup"><span data-stu-id="3724c-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="3724c-108">入力</span><span class="sxs-lookup"><span data-stu-id="3724c-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="3724c-109">結果: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3724c-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="3724c-110">またはが適用されているかどうかを判断するために使用される測定結果 `zeroOp` `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="3724c-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit-ctl"></a><span data-ttu-id="3724c-111">zeroOp: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="3724c-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="3724c-112">に適用される制御可能操作 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="3724c-112">The controllable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="3724c-113">ゼロ入力: ' t '</span><span class="sxs-lookup"><span data-stu-id="3724c-113">zeroInput : 'T</span></span>

<span data-ttu-id="3724c-114">時に提供される入力 `zeroOp` `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="3724c-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit-ctl"></a><span data-ttu-id="3724c-115">oneOp: ' U => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="3724c-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="3724c-116">に適用される制御可能操作 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="3724c-116">The controllable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="3724c-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="3724c-117">oneInput : 'U</span></span>

<span data-ttu-id="3724c-118">時に提供される入力 `oneOp` `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="3724c-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3724c-119">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3724c-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3724c-120">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="3724c-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3724c-121">&</span><span class="sxs-lookup"><span data-stu-id="3724c-121">'T</span></span>

<span data-ttu-id="3724c-122">`zeroOp`条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="3724c-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="3724c-123">' U</span><span class="sxs-lookup"><span data-stu-id="3724c-123">'U</span></span>

<span data-ttu-id="3724c-124">`oneOp`条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="3724c-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3724c-125">参照</span><span class="sxs-lookup"><span data-stu-id="3724c-125">See Also</span></span>

- [<span data-ttu-id="3724c-126">Microsoft. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="3724c-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="3724c-127">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="3724c-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="3724c-128">Microsoft.....。</span><span class="sxs-lookup"><span data-stu-id="3724c-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="3724c-129">Microsoft... ".."</span><span class="sxs-lookup"><span data-stu-id="3724c-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="3724c-130">Microsoft. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="3724c-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)