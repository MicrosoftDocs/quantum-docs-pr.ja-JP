---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719491"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="8cd64-102">_SwapOrderToPermuteArray 関数</span><span class="sxs-lookup"><span data-stu-id="8cd64-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="8cd64-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8cd64-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8cd64-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8cd64-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8cd64-105">順序付けされた配列を生成するために、配列内の順序要素を交換する必要があることを返します。</span><span class="sxs-lookup"><span data-stu-id="8cd64-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="8cd64-106">スワップが行われることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="8cd64-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="8cd64-107">入力</span><span class="sxs-lookup"><span data-stu-id="8cd64-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="8cd64-108">Ne・ Der: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8cd64-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8cd64-109">新しい配列のインデックスの順列を含む配列。</span><span class="sxs-lookup"><span data-stu-id="8cd64-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="8cd64-110">$ Elements $n が必要です。各要素は $0 $ から $n-$1 の一意の整数です。</span><span class="sxs-lookup"><span data-stu-id="8cd64-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="8cd64-111">出力: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="8cd64-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="8cd64-112">組は、スワップする2つのインデックスを表します。</span><span class="sxs-lookup"><span data-stu-id="8cd64-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="8cd64-113">スワップは最低のインデックスから開始されます。</span><span class="sxs-lookup"><span data-stu-id="8cd64-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="8cd64-114">解説</span><span class="sxs-lookup"><span data-stu-id="8cd64-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="8cd64-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="8cd64-115">Psuedocode</span></span>

<span data-ttu-id="8cd64-116">(インデックスが 0.. Length (Neの場合)-1) {while neの [index]! = index {Switch Neder [index] (ne、neて [index]]}})</span><span class="sxs-lookup"><span data-stu-id="8cd64-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>