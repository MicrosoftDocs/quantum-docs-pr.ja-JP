---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: Applyiの Ec 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: ebeec5b46567892ad30f194ababb42876ba08bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841751"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="dc1d9-102">Applyiの Ec 操作</span><span class="sxs-lookup"><span data-stu-id="dc1d9-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="dc1d9-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dc1d9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dc1d9-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc1d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc1d9-105">古典的な結果値が1であるという制御可能な操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="dc1d9-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="dc1d9-106">説明</span><span class="sxs-lookup"><span data-stu-id="dc1d9-106">Description</span></span>

<span data-ttu-id="dc1d9-107">`op`がの場合、操作と結果の値がに適用され `result` `op` `target` `result` `One` ます。</span><span class="sxs-lookup"><span data-stu-id="dc1d9-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="dc1d9-108">`Zero`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="dc1d9-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="dc1d9-109">サフィックスは、 `C` 適用される操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="dc1d9-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="dc1d9-110">入力</span><span class="sxs-lookup"><span data-stu-id="dc1d9-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="dc1d9-111">結果:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="dc1d9-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="dc1d9-112">Op が適用されるかどうかを制御する測定結果。</span><span class="sxs-lookup"><span data-stu-id="dc1d9-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="dc1d9-113">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="dc1d9-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="dc1d9-114">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="dc1d9-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="dc1d9-115">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="dc1d9-115">target : 'T</span></span>

<span data-ttu-id="dc1d9-116">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="dc1d9-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc1d9-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc1d9-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dc1d9-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc1d9-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc1d9-119">&</span><span class="sxs-lookup"><span data-stu-id="dc1d9-119">'T</span></span>

<span data-ttu-id="dc1d9-120">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="dc1d9-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc1d9-121">参照</span><span class="sxs-lookup"><span data-stu-id="dc1d9-121">See Also</span></span>

- [<span data-ttu-id="dc1d9-122">Microsoft. Canon. Applyi(Ec)</span><span class="sxs-lookup"><span data-stu-id="dc1d9-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="dc1d9-123">Microsoft. Canon. Applyi(Ea)</span><span class="sxs-lookup"><span data-stu-id="dc1d9-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="dc1d9-124">Microsoft. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="dc1d9-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)