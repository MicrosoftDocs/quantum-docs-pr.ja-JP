---
uid: Microsoft.Quantum.Arrays.All
title: All 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 345c3fb92babd4ae2e54803b6c3b79b3313ef417
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719479"
---
# <a name="all-function"></a><span data-ttu-id="b300c-102">All 関数</span><span class="sxs-lookup"><span data-stu-id="b300c-102">All function</span></span>

<span data-ttu-id="b300c-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b300c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b300c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b300c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b300c-105">配列と、配列の要素に対して定義されている述語が指定されている場合、配列のすべての要素が述語を満たすかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b300c-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="b300c-106">入力</span><span class="sxs-lookup"><span data-stu-id="b300c-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="b300c-107">述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b300c-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b300c-108">`'T` `Bool` 要素のチェックに使用されるからへの関数。</span><span class="sxs-lookup"><span data-stu-id="b300c-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="b300c-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="b300c-109">array : 'T[]</span></span>

<span data-ttu-id="b300c-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="b300c-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b300c-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b300c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b300c-112">`Bool`すべての要素に適用される述語の関数と関数の値。</span><span class="sxs-lookup"><span data-stu-id="b300c-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b300c-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="b300c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b300c-114">&</span><span class="sxs-lookup"><span data-stu-id="b300c-114">'T</span></span>

<span data-ttu-id="b300c-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="b300c-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="b300c-116">解説</span><span class="sxs-lookup"><span data-stu-id="b300c-116">Remarks</span></span>

<span data-ttu-id="b300c-117">関数は、ジェネリック型に対して定義されます。つまり、配列と関数がある場合は常に、 `'T[]` `predicate: 'T -> Bool` すべての要素が `Bool` 満たされるかどうかを示す値を生成でき `predicate` ます。</span><span class="sxs-lookup"><span data-stu-id="b300c-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>