---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Applyシリーズ Ofops 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841493"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="52585-102">Applyシリーズ Ofops 操作</span><span class="sxs-lookup"><span data-stu-id="52585-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="52585-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="52585-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="52585-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52585-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52585-105">Ops とそのターゲットの一覧を配列に順番に適用します。</span><span class="sxs-lookup"><span data-stu-id="52585-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="52585-106">入力</span><span class="sxs-lookup"><span data-stu-id="52585-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="52585-107">listOfOps: ' t [] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="52585-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="52585-108">適用する操作のリスト。それぞれ t 配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="52585-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="52585-109">これらは順番に適用され、最下位のインデックスが最初に適用されます。</span><span class="sxs-lookup"><span data-stu-id="52585-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="52585-110">ターゲット: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="52585-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="52585-111">Op のターゲットを記述する入れ子になった配列。</span><span class="sxs-lookup"><span data-stu-id="52585-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="52585-112">各配列には、使用するインデックスを記述する整数のリストを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="52585-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="52585-113">register: t []</span><span class="sxs-lookup"><span data-stu-id="52585-113">register : 'T[]</span></span>

<span data-ttu-id="52585-114">操作する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="52585-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="52585-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52585-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="52585-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="52585-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="52585-117">&</span><span class="sxs-lookup"><span data-stu-id="52585-117">'T</span></span>



## <a name="example"></a><span data-ttu-id="52585-118">例</span><span class="sxs-lookup"><span data-stu-id="52585-118">Example</span></span>

<span data-ttu-id="52585-119">次のようになります。 Exp ([P、Lix, P\n Liy], 0.5) は、qubits 0, 1//then X to qubits 2 let ops = [Exp ([P\n Lix, Pて Liy], 0.5, _), ApplyToFirstQubit (X, _)] です。let インデックス = [[0, 1], [2]];Applyシリーズ Ofops (ops, インデックス, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="52585-119">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubit(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOps(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="52585-120">参照</span><span class="sxs-lookup"><span data-stu-id="52585-120">See Also</span></span>

- [<span data-ttu-id="52585-121">Microsoft. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="52585-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)