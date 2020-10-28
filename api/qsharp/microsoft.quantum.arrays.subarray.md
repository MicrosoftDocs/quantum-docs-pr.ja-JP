---
uid: Microsoft.Quantum.Arrays.Subarray
title: サブ配列関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: be7b6ee1a396d67ebc311d8d97f4bd751a32d171
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718843"
---
# <a name="subarray-function"></a><span data-ttu-id="26f20-102">サブ配列関数</span><span class="sxs-lookup"><span data-stu-id="26f20-102">Subarray function</span></span>

<span data-ttu-id="26f20-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="26f20-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="26f20-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26f20-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26f20-105">配列と場所のリストを受け取り、指定した場所に一致する元の配列の要素から新しい配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="26f20-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="26f20-106">入力</span><span class="sxs-lookup"><span data-stu-id="26f20-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="26f20-107">インデックス: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="26f20-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="26f20-108">サブ配列を定義するために使用される整数のリスト。</span><span class="sxs-lookup"><span data-stu-id="26f20-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="26f20-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="26f20-109">array : 'T[]</span></span>

<span data-ttu-id="26f20-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="26f20-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="26f20-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="26f20-111">Output : 'T[]</span></span>

<span data-ttu-id="26f20-112">`out`インデックスがサブ配列に対応する要素の配列 `out[idx] == array[indices[idx]]` 。</span><span class="sxs-lookup"><span data-stu-id="26f20-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="26f20-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="26f20-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="26f20-114">&</span><span class="sxs-lookup"><span data-stu-id="26f20-114">'T</span></span>

<span data-ttu-id="26f20-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="26f20-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="26f20-116">解説</span><span class="sxs-lookup"><span data-stu-id="26f20-116">Remarks</span></span>

<span data-ttu-id="26f20-117">関数は、ジェネリック型に対して定義されます。つまり、配列と、サブ配列を定義している `'T[]` 場所のリストがある場合は、そのように定義されます。 `Int[]`</span><span class="sxs-lookup"><span data-stu-id="26f20-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="26f20-118">サブ配列の構築は、参照を維持するのではなく、指定された配列の新しいディープコピーを生成することに基づいています。</span><span class="sxs-lookup"><span data-stu-id="26f20-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="26f20-119">`Length(indices) < Length(array)`の場合、この関数はのサブセットを返し `array` ます。</span><span class="sxs-lookup"><span data-stu-id="26f20-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="26f20-120">一方、に `indices` 繰り返し要素が含まれている場合は、の対応する要素も `array` 同様に繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="26f20-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="26f20-121">`indices`との `array` 長さが同じである場合、この関数はの順列を提供 `array` します。</span><span class="sxs-lookup"><span data-stu-id="26f20-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>