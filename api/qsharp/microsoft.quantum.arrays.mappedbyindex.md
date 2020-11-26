---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 430495517974b641c249fa146aa9effec542e825
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209929"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="790ca-102">MappedByIndex 関数</span><span class="sxs-lookup"><span data-stu-id="790ca-102">MappedByIndex function</span></span>

<span data-ttu-id="790ca-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="790ca-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="790ca-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="790ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="790ca-105">配列と、配列のインデックス付き要素に対して定義された関数を指定すると、関数の下にある元の配列のイメージで構成される新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="790ca-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="790ca-106">入力</span><span class="sxs-lookup"><span data-stu-id="790ca-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="790ca-107">マッパー: ([Int](xref:microsoft.quantum.lang-ref.int), t)-> ' U</span><span class="sxs-lookup"><span data-stu-id="790ca-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="790ca-108">`(Int, 'T)` `'U` 要素とそのインデックスをマップするために使用されるからへの関数。</span><span class="sxs-lookup"><span data-stu-id="790ca-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="790ca-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="790ca-109">array : 'T[]</span></span>

<span data-ttu-id="790ca-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="790ca-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="790ca-111">出力: ' U []</span><span class="sxs-lookup"><span data-stu-id="790ca-111">Output : 'U[]</span></span>

<span data-ttu-id="790ca-112">`'U[]`関数によってマップされる要素の配列 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="790ca-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="790ca-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="790ca-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="790ca-114">&</span><span class="sxs-lookup"><span data-stu-id="790ca-114">'T</span></span>

<span data-ttu-id="790ca-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="790ca-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="790ca-116">' U</span><span class="sxs-lookup"><span data-stu-id="790ca-116">'U</span></span>

<span data-ttu-id="790ca-117">関数の結果の型 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="790ca-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="790ca-118">参照</span><span class="sxs-lookup"><span data-stu-id="790ca-118">See Also</span></span>

- [<span data-ttu-id="790ca-119">Microsoft. Quantum. マップ</span><span class="sxs-lookup"><span data-stu-id="790ca-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)