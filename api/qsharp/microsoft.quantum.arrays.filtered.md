---
uid: Microsoft.Quantum.Arrays.Filtered
title: フィルター処理された関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847157"
---
# <a name="filtered-function"></a><span data-ttu-id="7c73b-102">フィルター処理された関数</span><span class="sxs-lookup"><span data-stu-id="7c73b-102">Filtered function</span></span>

<span data-ttu-id="7c73b-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7c73b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7c73b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c73b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c73b-105">配列と、配列の要素に対して定義された述語が指定されている場合、は述語を満たす要素で構成される配列を返します。</span><span class="sxs-lookup"><span data-stu-id="7c73b-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="7c73b-106">入力</span><span class="sxs-lookup"><span data-stu-id="7c73b-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="7c73b-107">述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7c73b-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7c73b-108">`'T`要素をフィルター処理するために使用されるブール値からブール型への関数。</span><span class="sxs-lookup"><span data-stu-id="7c73b-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="7c73b-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="7c73b-109">array : 'T[]</span></span>

<span data-ttu-id="7c73b-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="7c73b-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="7c73b-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="7c73b-111">Output : 'T[]</span></span>

<span data-ttu-id="7c73b-112">述語を `'T[]` 満たす要素の配列。</span><span class="sxs-lookup"><span data-stu-id="7c73b-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7c73b-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c73b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7c73b-114">&</span><span class="sxs-lookup"><span data-stu-id="7c73b-114">'T</span></span>

<span data-ttu-id="7c73b-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="7c73b-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="7c73b-116">例</span><span class="sxs-lookup"><span data-stu-id="7c73b-116">Example</span></span>

<span data-ttu-id="7c73b-117">次のコードは、"Filtered" 関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="7c73b-117">The following code demonstrates the "Filtered" function.</span></span>
<span data-ttu-id="7c73b-118">述語は、関数を使用して定義され @"microsoft.quantum.logical.greaterthani" ます。</span><span class="sxs-lookup"><span data-stu-id="7c73b-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

<span data-ttu-id="7c73b-119">この例で期待される結果は、5より大きい数値の配列になります。</span><span class="sxs-lookup"><span data-stu-id="7c73b-119">The outcome one should expect from this example will be an array of numbers greater than 5.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c73b-120">解説</span><span class="sxs-lookup"><span data-stu-id="7c73b-120">Remarks</span></span>

<span data-ttu-id="7c73b-121">関数は、ジェネリック型に対して定義されます。つまり、配列と述語がある場合は、 `'T[]` `'T -> Bool` 要素をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="7c73b-121">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>