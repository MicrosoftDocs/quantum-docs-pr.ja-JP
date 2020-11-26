---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Applyシリーズ Ofops 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b8810e7d31689046e72905195a3a25ef80fc8d67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218004"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="702de-102">Applyシリーズ Ofops 操作</span><span class="sxs-lookup"><span data-stu-id="702de-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="702de-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="702de-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="702de-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="702de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="702de-105">Ops とそのターゲットの一覧を配列に順番に適用します。</span><span class="sxs-lookup"><span data-stu-id="702de-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="702de-106">入力</span><span class="sxs-lookup"><span data-stu-id="702de-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="702de-107">listOfOps: ' t [] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="702de-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="702de-108">適用する操作のリスト。それぞれ t 配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="702de-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="702de-109">これらは順番に適用され、最下位のインデックスが最初に適用されます。</span><span class="sxs-lookup"><span data-stu-id="702de-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="702de-110">ターゲット: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="702de-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="702de-111">Op のターゲットを記述する入れ子になった配列。</span><span class="sxs-lookup"><span data-stu-id="702de-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="702de-112">各配列には、使用するインデックスを記述する整数のリストを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="702de-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="702de-113">register: t []</span><span class="sxs-lookup"><span data-stu-id="702de-113">register : 'T[]</span></span>

<span data-ttu-id="702de-114">操作する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="702de-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="702de-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="702de-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="702de-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="702de-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="702de-117">&</span><span class="sxs-lookup"><span data-stu-id="702de-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="702de-118">参照</span><span class="sxs-lookup"><span data-stu-id="702de-118">See Also</span></span>

- [<span data-ttu-id="702de-119">Microsoft. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="702de-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)