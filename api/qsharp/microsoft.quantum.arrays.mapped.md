---
uid: Microsoft.Quantum.Arrays.Mapped
title: マップされた関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 1abb9d6fb1a921b49554bef968442f4f2b346b71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719078"
---
# <a name="mapped-function"></a><span data-ttu-id="63aa6-102">マップされた関数</span><span class="sxs-lookup"><span data-stu-id="63aa6-102">Mapped function</span></span>

<span data-ttu-id="63aa6-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="63aa6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="63aa6-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63aa6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63aa6-105">配列と、配列の要素に対して定義されている関数を指定すると、関数の下にある元の配列のイメージで構成される新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="63aa6-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="63aa6-106">入力</span><span class="sxs-lookup"><span data-stu-id="63aa6-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="63aa6-107">マッパー: > ' U</span><span class="sxs-lookup"><span data-stu-id="63aa6-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="63aa6-108">`'T` `'U` 要素をマップするために使用されるからへの関数。</span><span class="sxs-lookup"><span data-stu-id="63aa6-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="63aa6-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="63aa6-109">array : 'T[]</span></span>

<span data-ttu-id="63aa6-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="63aa6-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="63aa6-111">出力: ' U []</span><span class="sxs-lookup"><span data-stu-id="63aa6-111">Output : 'U[]</span></span>

<span data-ttu-id="63aa6-112">`'U[]`関数によってマップされる要素の配列 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="63aa6-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="63aa6-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="63aa6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="63aa6-114">&</span><span class="sxs-lookup"><span data-stu-id="63aa6-114">'T</span></span>

<span data-ttu-id="63aa6-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="63aa6-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="63aa6-116">' U</span><span class="sxs-lookup"><span data-stu-id="63aa6-116">'U</span></span>

<span data-ttu-id="63aa6-117">関数の結果の型 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="63aa6-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="63aa6-118">解説</span><span class="sxs-lookup"><span data-stu-id="63aa6-118">Remarks</span></span>

<span data-ttu-id="63aa6-119">関数は、ジェネリック型に対して定義されます。つまり、配列と関数がある場合は、 `'T[]` `mapper: 'T -> 'U` 配列の要素をマップし、型の新しい配列を生成でき `'U[]` ます。</span><span class="sxs-lookup"><span data-stu-id="63aa6-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>