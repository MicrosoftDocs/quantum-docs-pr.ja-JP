---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: d63b204334611f8f2c3860f9ee1d756f637780e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221013"
---
# <a name="indexof-function"></a><span data-ttu-id="bf5e2-102">IndexOf 関数</span><span class="sxs-lookup"><span data-stu-id="bf5e2-102">IndexOf function</span></span>

<span data-ttu-id="bf5e2-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bf5e2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bf5e2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bf5e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bf5e2-105">指定された述語を満たす配列内の最初の要素の最初のインデックスを返します。</span><span class="sxs-lookup"><span data-stu-id="bf5e2-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="bf5e2-106">そのような要素が存在しない場合は、-1 を返します。</span><span class="sxs-lookup"><span data-stu-id="bf5e2-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="bf5e2-107">入力</span><span class="sxs-lookup"><span data-stu-id="bf5e2-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="bf5e2-108">述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bf5e2-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bf5e2-109">配列の要素に対して動作する述語関数。</span><span class="sxs-lookup"><span data-stu-id="bf5e2-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="bf5e2-110">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="bf5e2-110">arr : 'T[]</span></span>

<span data-ttu-id="bf5e2-111">指定された述語を使用して検索される配列。</span><span class="sxs-lookup"><span data-stu-id="bf5e2-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="bf5e2-112">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bf5e2-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bf5e2-113">`idx`が true であるような最小のインデックス `predicate(arr[idx])` 。そのような要素が存在しない場合は-1。</span><span class="sxs-lookup"><span data-stu-id="bf5e2-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bf5e2-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf5e2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bf5e2-115">&</span><span class="sxs-lookup"><span data-stu-id="bf5e2-115">'T</span></span>

