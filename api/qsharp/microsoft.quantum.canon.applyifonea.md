---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: Applyiの Ea 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 1593f565e950a9410df0ae9de59e6d0e6a7b99b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844932"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="cb270-102">Applyiの Ea 操作</span><span class="sxs-lookup"><span data-stu-id="cb270-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="cb270-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cb270-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cb270-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb270-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb270-105">従来の結果値が1である adjointable 操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="cb270-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="cb270-106">説明</span><span class="sxs-lookup"><span data-stu-id="cb270-106">Description</span></span>

<span data-ttu-id="cb270-107">`op`がの場合、操作と結果の値がに適用され `result` `op` `target` `result` `One` ます。</span><span class="sxs-lookup"><span data-stu-id="cb270-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="cb270-108">`Zero`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="cb270-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="cb270-109">サフィックスは、 `A` 適用される操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="cb270-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="cb270-110">入力</span><span class="sxs-lookup"><span data-stu-id="cb270-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="cb270-111">結果:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="cb270-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="cb270-112">Op が適用されるかどうかを制御する測定結果。</span><span class="sxs-lookup"><span data-stu-id="cb270-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="cb270-113">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="cb270-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="cb270-114">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="cb270-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="cb270-115">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="cb270-115">target : 'T</span></span>

<span data-ttu-id="cb270-116">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="cb270-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb270-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb270-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cb270-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb270-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cb270-119">&</span><span class="sxs-lookup"><span data-stu-id="cb270-119">'T</span></span>

<span data-ttu-id="cb270-120">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="cb270-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb270-121">参照</span><span class="sxs-lookup"><span data-stu-id="cb270-121">See Also</span></span>

- [<span data-ttu-id="cb270-122">Microsoft. Canon. Applyi(Ec)</span><span class="sxs-lookup"><span data-stu-id="cb270-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="cb270-123">Microsoft. Canon. Applyi(Ea)</span><span class="sxs-lookup"><span data-stu-id="cb270-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="cb270-124">Microsoft. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="cb270-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)