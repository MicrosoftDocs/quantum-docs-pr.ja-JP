---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: ApplyIfElseR 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 0d7cc9f67f9dd0c69a9256f007a3aeab3e457907
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841809"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="f4fcc-102">ApplyIfElseR 操作</span><span class="sxs-lookup"><span data-stu-id="f4fcc-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="f4fcc-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f4fcc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f4fcc-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4fcc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4fcc-105">古典的な結果の値に応じて、2つの操作のいずれかを適用します。</span><span class="sxs-lookup"><span data-stu-id="f4fcc-105">Applies one of two operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="f4fcc-106">説明</span><span class="sxs-lookup"><span data-stu-id="f4fcc-106">Description</span></span>

<span data-ttu-id="f4fcc-107">結果が返された場合 `result` 、 `zeroOp` `zeroInput` は、がと等しいときにを入力として操作を適用し、when にを `result` 適用し `Zero` `oneOp(oneInput)` `result == One` ます。</span><span class="sxs-lookup"><span data-stu-id="f4fcc-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="f4fcc-108">入力</span><span class="sxs-lookup"><span data-stu-id="f4fcc-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="f4fcc-109">結果:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="f4fcc-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="f4fcc-110">またはが適用されているかどうかを判断するために使用される測定結果 `zeroOp` `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="f4fcc-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit"></a><span data-ttu-id="f4fcc-111">zeroOp: t => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f4fcc-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f4fcc-112">に適用される操作 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="f4fcc-112">The operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="f4fcc-113">ゼロ入力: ' t '</span><span class="sxs-lookup"><span data-stu-id="f4fcc-113">zeroInput : 'T</span></span>

<span data-ttu-id="f4fcc-114">時に提供される入力 `zeroOp` `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="f4fcc-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit"></a><span data-ttu-id="f4fcc-115">oneOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f4fcc-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f4fcc-116">に適用される操作 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="f4fcc-116">The operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="f4fcc-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="f4fcc-117">oneInput : 'U</span></span>

<span data-ttu-id="f4fcc-118">時に提供される入力 `oneOp` `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="f4fcc-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f4fcc-119">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f4fcc-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f4fcc-120">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="f4fcc-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f4fcc-121">&</span><span class="sxs-lookup"><span data-stu-id="f4fcc-121">'T</span></span>

<span data-ttu-id="f4fcc-122">`zeroOp`条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="f4fcc-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="f4fcc-123">' U</span><span class="sxs-lookup"><span data-stu-id="f4fcc-123">'U</span></span>

<span data-ttu-id="f4fcc-124">`oneOp`条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="f4fcc-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4fcc-125">参照</span><span class="sxs-lookup"><span data-stu-id="f4fcc-125">See Also</span></span>

- [<span data-ttu-id="f4fcc-126">Microsoft. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="f4fcc-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="f4fcc-127">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="f4fcc-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="f4fcc-128">Microsoft.....。</span><span class="sxs-lookup"><span data-stu-id="f4fcc-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="f4fcc-129">Microsoft... ".."</span><span class="sxs-lookup"><span data-stu-id="f4fcc-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="f4fcc-130">Microsoft. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="f4fcc-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)