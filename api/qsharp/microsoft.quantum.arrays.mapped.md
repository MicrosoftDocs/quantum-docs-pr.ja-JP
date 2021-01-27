---
uid: Microsoft.Quantum.Arrays.Mapped
title: マップされた関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 00ea0803faf6e8edfa748af63dd6c7e217b1de41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845685"
---
# <a name="mapped-function"></a><span data-ttu-id="c18a0-102">マップされた関数</span><span class="sxs-lookup"><span data-stu-id="c18a0-102">Mapped function</span></span>

<span data-ttu-id="c18a0-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c18a0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c18a0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c18a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c18a0-105">配列と、配列の要素に対して定義されている関数を指定すると、関数の下にある元の配列のイメージで構成される新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="c18a0-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="c18a0-106">入力</span><span class="sxs-lookup"><span data-stu-id="c18a0-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="c18a0-107">マッパー: > ' U</span><span class="sxs-lookup"><span data-stu-id="c18a0-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="c18a0-108">`'T` `'U` 要素をマップするために使用されるからへの関数。</span><span class="sxs-lookup"><span data-stu-id="c18a0-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="c18a0-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="c18a0-109">array : 'T[]</span></span>

<span data-ttu-id="c18a0-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="c18a0-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="c18a0-111">出力: ' U []</span><span class="sxs-lookup"><span data-stu-id="c18a0-111">Output : 'U[]</span></span>

<span data-ttu-id="c18a0-112">`'U[]`関数によってマップされる要素の配列 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="c18a0-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c18a0-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="c18a0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c18a0-114">&</span><span class="sxs-lookup"><span data-stu-id="c18a0-114">'T</span></span>

<span data-ttu-id="c18a0-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="c18a0-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="c18a0-116">' U</span><span class="sxs-lookup"><span data-stu-id="c18a0-116">'U</span></span>

<span data-ttu-id="c18a0-117">関数の結果の型 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="c18a0-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="c18a0-118">解説</span><span class="sxs-lookup"><span data-stu-id="c18a0-118">Remarks</span></span>

<span data-ttu-id="c18a0-119">関数は、ジェネリック型に対して定義されます。つまり、配列と関数がある場合は、 `'T[]` `mapper: 'T -> 'U` 配列の要素をマップし、型の新しい配列を生成でき `'U[]` ます。</span><span class="sxs-lookup"><span data-stu-id="c18a0-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>