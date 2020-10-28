---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Applyシリーズ Ofops 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: aff0bcb831960153166e88aef1f05e000125d5d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717670"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="5339e-102">Applyシリーズ Ofops 操作</span><span class="sxs-lookup"><span data-stu-id="5339e-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="5339e-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5339e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5339e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5339e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5339e-105">Ops とそのターゲットの一覧を配列に順番に適用します。</span><span class="sxs-lookup"><span data-stu-id="5339e-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5339e-106">入力</span><span class="sxs-lookup"><span data-stu-id="5339e-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="5339e-107">listOfOps: ' t [] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="5339e-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="5339e-108">適用する操作のリスト。それぞれ t 配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="5339e-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="5339e-109">これらは順番に適用され、最下位のインデックスが最初に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5339e-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="5339e-110">ターゲット: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="5339e-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="5339e-111">Op のターゲットを記述する入れ子になった配列。</span><span class="sxs-lookup"><span data-stu-id="5339e-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="5339e-112">各配列には、使用するインデックスを記述する整数のリストを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5339e-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="5339e-113">register: t []</span><span class="sxs-lookup"><span data-stu-id="5339e-113">register : 'T[]</span></span>

<span data-ttu-id="5339e-114">操作する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="5339e-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5339e-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5339e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5339e-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="5339e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5339e-117">&</span><span class="sxs-lookup"><span data-stu-id="5339e-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="5339e-118">参照</span><span class="sxs-lookup"><span data-stu-id="5339e-118">See Also</span></span>

- [<span data-ttu-id="5339e-119">Microsoft. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="5339e-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)