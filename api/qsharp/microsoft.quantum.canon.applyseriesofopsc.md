---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Applyシリーズ Ofopsc 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: 308256833dc607f685e3a5f2278e374cf3b6ce22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844642"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="e0e6d-102">Applyシリーズ Ofopsc 操作</span><span class="sxs-lookup"><span data-stu-id="e0e6d-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="e0e6d-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e0e6d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e0e6d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0e6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0e6d-105">Ops とそのターゲットの一覧を配列に順番に適用します。</span><span class="sxs-lookup"><span data-stu-id="e0e6d-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="e0e6d-106">た</span><span class="sxs-lookup"><span data-stu-id="e0e6d-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="e0e6d-107">入力</span><span class="sxs-lookup"><span data-stu-id="e0e6d-107">Input</span></span>

### <a name="listofops--t--unit--is-ctl"></a><span data-ttu-id="e0e6d-108">listOfOps: ' t [] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl []</span><span class="sxs-lookup"><span data-stu-id="e0e6d-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="e0e6d-109">適用する操作のリスト。それぞれ t 配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="e0e6d-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="e0e6d-110">これらは順番に適用され、最下位のインデックスが最初に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e0e6d-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="e0e6d-111">各には、管理されたファンクタが必要です。</span><span class="sxs-lookup"><span data-stu-id="e0e6d-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="e0e6d-112">ターゲット: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="e0e6d-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="e0e6d-113">Op のターゲットを記述する入れ子になった配列。</span><span class="sxs-lookup"><span data-stu-id="e0e6d-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="e0e6d-114">各配列には、使用するインデックスを記述する整数のリストを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0e6d-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="e0e6d-115">register: t []</span><span class="sxs-lookup"><span data-stu-id="e0e6d-115">register : 'T[]</span></span>

<span data-ttu-id="e0e6d-116">操作する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="e0e6d-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e0e6d-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e0e6d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e0e6d-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0e6d-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e0e6d-119">&</span><span class="sxs-lookup"><span data-stu-id="e0e6d-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="e0e6d-120">例</span><span class="sxs-lookup"><span data-stu-id="e0e6d-120">Example</span></span>

<span data-ttu-id="e0e6d-121">次のようになります。 Exp ([P\n Lix, P、p、p、および 0.5) を qubits 0、1//then X to qubits 2 let ops = [Exp ([P\n Lix, Pて Liy], 0.5, _)、ApplyToFirstQubitC (X, _)] です。let インデックス = [[0, 1], [2]];Applyシリーズ Ofopsc (ops, インデックス, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="e0e6d-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitC(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsC(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="e0e6d-122">参照</span><span class="sxs-lookup"><span data-stu-id="e0e6d-122">See Also</span></span>

- [<span data-ttu-id="e0e6d-123">Microsoft. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="e0e6d-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)