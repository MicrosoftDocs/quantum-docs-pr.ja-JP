---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: Applyiの Ea 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 76c15aba6042c2801ecfe8470e82099c54ba3846
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718095"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="f7c97-102">Applyiの Ea 操作</span><span class="sxs-lookup"><span data-stu-id="f7c97-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="f7c97-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7c97-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7c97-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7c97-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7c97-105">従来の結果値が1である adjointable 操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="f7c97-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="f7c97-106">説明</span><span class="sxs-lookup"><span data-stu-id="f7c97-106">Description</span></span>

<span data-ttu-id="f7c97-107">`op`がの場合、操作と結果の値がに適用され `result` `op` `target` `result` `One` ます。</span><span class="sxs-lookup"><span data-stu-id="f7c97-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="f7c97-108">`Zero`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="f7c97-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="f7c97-109">サフィックスは、 `A` 適用される操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="f7c97-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="f7c97-110">入力</span><span class="sxs-lookup"><span data-stu-id="f7c97-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="f7c97-111">結果: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="f7c97-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="f7c97-112">Op が適用されるかどうかを制御する測定結果。</span><span class="sxs-lookup"><span data-stu-id="f7c97-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="f7c97-113">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="f7c97-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f7c97-114">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="f7c97-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="f7c97-115">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="f7c97-115">target : 'T</span></span>

<span data-ttu-id="f7c97-116">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="f7c97-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7c97-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7c97-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f7c97-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7c97-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7c97-119">&</span><span class="sxs-lookup"><span data-stu-id="f7c97-119">'T</span></span>

<span data-ttu-id="f7c97-120">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="f7c97-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7c97-121">参照</span><span class="sxs-lookup"><span data-stu-id="f7c97-121">See Also</span></span>

- [<span data-ttu-id="f7c97-122">Microsoft. Canon. Applyi(Ec)</span><span class="sxs-lookup"><span data-stu-id="f7c97-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="f7c97-123">Microsoft. Canon. Applyi(Ea)</span><span class="sxs-lookup"><span data-stu-id="f7c97-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="f7c97-124">Microsoft. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="f7c97-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)