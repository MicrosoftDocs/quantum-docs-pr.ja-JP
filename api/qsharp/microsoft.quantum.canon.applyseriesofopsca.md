---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: Applyシリーズ Ofopsca 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 2327a693e528cf46f95eae5ee052e9dd9b6ee187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717633"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="50915-102">Applyシリーズ Ofopsca 操作</span><span class="sxs-lookup"><span data-stu-id="50915-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="50915-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="50915-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="50915-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50915-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50915-105">Ops とそのターゲットの一覧を配列に順番に適用します。</span><span class="sxs-lookup"><span data-stu-id="50915-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="50915-106">(Adjoint + 制御)</span><span class="sxs-lookup"><span data-stu-id="50915-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="50915-107">入力</span><span class="sxs-lookup"><span data-stu-id="50915-107">Input</span></span>

### <a name="listofops--t--unit-adj--ctl"></a><span data-ttu-id="50915-108">listOfOps: ' t [] => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="50915-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="50915-109">適用する操作のリスト。それぞれ t 配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="50915-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="50915-110">これらは順番に適用され、最下位のインデックスが最初に適用されます。</span><span class="sxs-lookup"><span data-stu-id="50915-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="50915-111">各には、Adjoint と制御されたファンクタの両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="50915-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="50915-112">ターゲット: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="50915-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="50915-113">Op のターゲットを記述する入れ子になった配列。</span><span class="sxs-lookup"><span data-stu-id="50915-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="50915-114">各配列には、使用するインデックスを記述する整数のリストを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="50915-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="50915-115">register: t []</span><span class="sxs-lookup"><span data-stu-id="50915-115">register : 'T[]</span></span>

<span data-ttu-id="50915-116">操作する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="50915-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="50915-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50915-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="50915-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="50915-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50915-119">&</span><span class="sxs-lookup"><span data-stu-id="50915-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="50915-120">参照</span><span class="sxs-lookup"><span data-stu-id="50915-120">See Also</span></span>

- [<span data-ttu-id="50915-121">Microsoft. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="50915-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)