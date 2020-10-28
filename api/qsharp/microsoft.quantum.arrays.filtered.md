---
uid: Microsoft.Quantum.Arrays.Filtered
title: フィルター処理された関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 4c786c69b0896b517f108611e32501867838aeb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719270"
---
# <a name="filtered-function"></a><span data-ttu-id="a9e0a-102">フィルター処理された関数</span><span class="sxs-lookup"><span data-stu-id="a9e0a-102">Filtered function</span></span>

<span data-ttu-id="a9e0a-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a9e0a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a9e0a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9e0a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9e0a-105">配列と、配列の要素に対して定義された述語が指定されている場合、は述語を満たす要素で構成される配列を返します。</span><span class="sxs-lookup"><span data-stu-id="a9e0a-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="a9e0a-106">入力</span><span class="sxs-lookup"><span data-stu-id="a9e0a-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="a9e0a-107">述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a9e0a-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a9e0a-108">`'T`要素をフィルター処理するために使用されるブール値からブール型への関数。</span><span class="sxs-lookup"><span data-stu-id="a9e0a-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="a9e0a-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="a9e0a-109">array : 'T[]</span></span>

<span data-ttu-id="a9e0a-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="a9e0a-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="a9e0a-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="a9e0a-111">Output : 'T[]</span></span>

<span data-ttu-id="a9e0a-112">述語を `'T[]` 満たす要素の配列。</span><span class="sxs-lookup"><span data-stu-id="a9e0a-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a9e0a-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a9e0a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a9e0a-114">&</span><span class="sxs-lookup"><span data-stu-id="a9e0a-114">'T</span></span>

<span data-ttu-id="a9e0a-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="a9e0a-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="a9e0a-116">解説</span><span class="sxs-lookup"><span data-stu-id="a9e0a-116">Remarks</span></span>

<span data-ttu-id="a9e0a-117">関数は、ジェネリック型に対して定義されます。つまり、配列と述語がある場合は、 `'T[]` `'T -> Bool` 要素をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="a9e0a-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>