---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845661"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="cb862-102">MappedByIndex 関数</span><span class="sxs-lookup"><span data-stu-id="cb862-102">MappedByIndex function</span></span>

<span data-ttu-id="cb862-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cb862-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cb862-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb862-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb862-105">配列と、配列のインデックス付き要素に対して定義された関数を指定すると、関数の下にある元の配列のイメージで構成される新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="cb862-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="cb862-106">入力</span><span class="sxs-lookup"><span data-stu-id="cb862-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="cb862-107">マッパー: ([Int](xref:microsoft.quantum.lang-ref.int), t)-> ' U</span><span class="sxs-lookup"><span data-stu-id="cb862-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="cb862-108">`(Int, 'T)` `'U` 要素とそのインデックスをマップするために使用されるからへの関数。</span><span class="sxs-lookup"><span data-stu-id="cb862-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="cb862-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="cb862-109">array : 'T[]</span></span>

<span data-ttu-id="cb862-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="cb862-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="cb862-111">出力: ' U []</span><span class="sxs-lookup"><span data-stu-id="cb862-111">Output : 'U[]</span></span>

<span data-ttu-id="cb862-112">`'U[]`関数によってマップされる要素の配列 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="cb862-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cb862-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb862-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cb862-114">&</span><span class="sxs-lookup"><span data-stu-id="cb862-114">'T</span></span>

<span data-ttu-id="cb862-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="cb862-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="cb862-116">' U</span><span class="sxs-lookup"><span data-stu-id="cb862-116">'U</span></span>

<span data-ttu-id="cb862-117">関数の結果の型 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="cb862-117">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="cb862-118">例</span><span class="sxs-lookup"><span data-stu-id="cb862-118">Example</span></span>

<span data-ttu-id="cb862-119">次の2つの行は等価です。</span><span class="sxs-lookup"><span data-stu-id="cb862-119">The following two lines are equivalent:</span></span>

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

<span data-ttu-id="cb862-120">and</span><span class="sxs-lookup"><span data-stu-id="cb862-120">and</span></span>

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a><span data-ttu-id="cb862-121">参照</span><span class="sxs-lookup"><span data-stu-id="cb862-121">See Also</span></span>

- [<span data-ttu-id="cb862-122">Microsoft. Quantum. マップ</span><span class="sxs-lookup"><span data-stu-id="cb862-122">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)