---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: Applyiの Ec 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 24a00d83c1bbe6b07adb27c58fc70bc76af0a910
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209419"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="3ee74-102">Applyiの Ec 操作</span><span class="sxs-lookup"><span data-stu-id="3ee74-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="3ee74-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3ee74-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3ee74-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ee74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ee74-105">古典的な結果値が1であるという制御可能な操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="3ee74-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="3ee74-106">説明</span><span class="sxs-lookup"><span data-stu-id="3ee74-106">Description</span></span>

<span data-ttu-id="3ee74-107">`op`がの場合、操作と結果の値がに適用され `result` `op` `target` `result` `One` ます。</span><span class="sxs-lookup"><span data-stu-id="3ee74-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="3ee74-108">`Zero`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="3ee74-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="3ee74-109">サフィックスは、 `C` 適用される操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ee74-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="3ee74-110">入力</span><span class="sxs-lookup"><span data-stu-id="3ee74-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="3ee74-111">結果:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3ee74-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="3ee74-112">Op が適用されるかどうかを制御する測定結果。</span><span class="sxs-lookup"><span data-stu-id="3ee74-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="3ee74-113">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="3ee74-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3ee74-114">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="3ee74-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="3ee74-115">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="3ee74-115">target : 'T</span></span>

<span data-ttu-id="3ee74-116">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="3ee74-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ee74-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ee74-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3ee74-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="3ee74-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3ee74-119">&</span><span class="sxs-lookup"><span data-stu-id="3ee74-119">'T</span></span>

<span data-ttu-id="3ee74-120">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="3ee74-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ee74-121">参照</span><span class="sxs-lookup"><span data-stu-id="3ee74-121">See Also</span></span>

- [<span data-ttu-id="3ee74-122">Microsoft. Canon. Applyi(Ec)</span><span class="sxs-lookup"><span data-stu-id="3ee74-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="3ee74-123">Microsoft. Canon. Applyi(Ea)</span><span class="sxs-lookup"><span data-stu-id="3ee74-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="3ee74-124">Microsoft. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="3ee74-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)