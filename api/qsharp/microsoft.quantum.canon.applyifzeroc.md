---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: Applyifゼロ c 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: cfc2a659f4da011baadff1a0d6a20a2a36d0a285
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718011"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="d0d9f-102">Applyifゼロ c 操作</span><span class="sxs-lookup"><span data-stu-id="d0d9f-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="d0d9f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d0d9f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d0d9f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0d9f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0d9f-105">古典的な結果値が0である制御可能な操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="d0d9f-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="d0d9f-106">説明</span><span class="sxs-lookup"><span data-stu-id="d0d9f-106">Description</span></span>

<span data-ttu-id="d0d9f-107">`op`がの場合、操作と結果の値がに適用され `result` `op` `target` `result` `Zero` ます。</span><span class="sxs-lookup"><span data-stu-id="d0d9f-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="d0d9f-108">`One`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="d0d9f-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="d0d9f-109">サフィックスは、 `C` 適用される操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="d0d9f-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="d0d9f-110">入力</span><span class="sxs-lookup"><span data-stu-id="d0d9f-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="d0d9f-111">結果: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="d0d9f-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="d0d9f-112">Op が適用されるかどうかを制御する測定結果。</span><span class="sxs-lookup"><span data-stu-id="d0d9f-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="d0d9f-113">op: ' t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="d0d9f-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="d0d9f-114">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="d0d9f-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="d0d9f-115">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="d0d9f-115">target : 'T</span></span>

<span data-ttu-id="d0d9f-116">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="d0d9f-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0d9f-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0d9f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d0d9f-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0d9f-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0d9f-119">&</span><span class="sxs-lookup"><span data-stu-id="d0d9f-119">'T</span></span>

<span data-ttu-id="d0d9f-120">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="d0d9f-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0d9f-121">参照</span><span class="sxs-lookup"><span data-stu-id="d0d9f-121">See Also</span></span>

- [<span data-ttu-id="d0d9f-122">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="d0d9f-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="d0d9f-123">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="d0d9f-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="d0d9f-124">Microsoft. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="d0d9f-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)