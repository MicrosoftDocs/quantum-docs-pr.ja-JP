---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719042"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="9ff60-102">MappedOverRange 関数</span><span class="sxs-lookup"><span data-stu-id="9ff60-102">MappedOverRange function</span></span>

<span data-ttu-id="9ff60-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9ff60-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9ff60-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9ff60-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9ff60-105">入力として整数を受け取る範囲と関数を指定した場合は、関数の下の範囲値のイメージで構成される新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="9ff60-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="9ff60-106">入力</span><span class="sxs-lookup"><span data-stu-id="9ff60-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="9ff60-107">マッパー: [Int](xref:microsoft.quantum.lang-ref.int) -> t</span><span class="sxs-lookup"><span data-stu-id="9ff60-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="9ff60-108">`Int` `'T` 範囲値をマップするために使用されるからへの関数。</span><span class="sxs-lookup"><span data-stu-id="9ff60-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="9ff60-109">範囲: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="9ff60-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="9ff60-110">整数の範囲。</span><span class="sxs-lookup"><span data-stu-id="9ff60-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="9ff60-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="9ff60-111">Output : 'T[]</span></span>

<span data-ttu-id="9ff60-112">`'T[]`関数によってマップされる要素の配列 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="9ff60-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9ff60-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ff60-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9ff60-114">&</span><span class="sxs-lookup"><span data-stu-id="9ff60-114">'T</span></span>

<span data-ttu-id="9ff60-115">関数の結果の型 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="9ff60-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="9ff60-116">解説</span><span class="sxs-lookup"><span data-stu-id="9ff60-116">Remarks</span></span>

<span data-ttu-id="9ff60-117">関数は、ジェネリック型に対して定義されます。つまり、関数がある場合は、 `mapper: Int -> 'T` 範囲の値をマップし、型の配列を生成でき `'T[]` ます。</span><span class="sxs-lookup"><span data-stu-id="9ff60-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ff60-118">参照</span><span class="sxs-lookup"><span data-stu-id="9ff60-118">See Also</span></span>

- [<span data-ttu-id="9ff60-119">Microsoft. Quantum. マップ</span><span class="sxs-lookup"><span data-stu-id="9ff60-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)