---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719203"
---
# <a name="foreach-operation"></a><span data-ttu-id="a48b3-102">ForEach 操作</span><span class="sxs-lookup"><span data-stu-id="a48b3-102">ForEach operation</span></span>

<span data-ttu-id="a48b3-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a48b3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a48b3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a48b3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a48b3-105">配列と、配列の要素に対して定義されている操作が指定された場合、は、操作の下にある元の配列のイメージで構成される新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="a48b3-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="a48b3-106">入力</span><span class="sxs-lookup"><span data-stu-id="a48b3-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="a48b3-107">アクション: ' t => ' U</span><span class="sxs-lookup"><span data-stu-id="a48b3-107">action : 'T => 'U</span></span> 

<span data-ttu-id="a48b3-108">`'T` `'U` 各要素に適用されるからへの操作。</span><span class="sxs-lookup"><span data-stu-id="a48b3-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="a48b3-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="a48b3-109">array : 'T[]</span></span>

<span data-ttu-id="a48b3-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="a48b3-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="a48b3-111">出力: ' U []</span><span class="sxs-lookup"><span data-stu-id="a48b3-111">Output : 'U[]</span></span>

<span data-ttu-id="a48b3-112">`'U[]`操作によってマップされる要素の配列 `action` 。</span><span class="sxs-lookup"><span data-stu-id="a48b3-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a48b3-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a48b3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a48b3-114">&</span><span class="sxs-lookup"><span data-stu-id="a48b3-114">'T</span></span>

<span data-ttu-id="a48b3-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="a48b3-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="a48b3-116">' U</span><span class="sxs-lookup"><span data-stu-id="a48b3-116">'U</span></span>

<span data-ttu-id="a48b3-117">操作の結果の種類 `action` 。</span><span class="sxs-lookup"><span data-stu-id="a48b3-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="a48b3-118">解説</span><span class="sxs-lookup"><span data-stu-id="a48b3-118">Remarks</span></span>

<span data-ttu-id="a48b3-119">この操作は、ジェネリック型に対して定義されます。つまり、配列と操作がある場合は、 `'T[]` `action : 'T -> 'U` 配列の要素をマップし、型の新しい配列を生成でき `'U[]` ます。</span><span class="sxs-lookup"><span data-stu-id="a48b3-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>