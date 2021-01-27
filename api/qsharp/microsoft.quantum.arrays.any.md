---
uid: Microsoft.Quantum.Arrays.Any
title: すべての関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: a05f9531168bf2b32977665d38cc00f3c8e64879
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846275"
---
# <a name="any-function"></a><span data-ttu-id="1eab4-102">すべての関数</span><span class="sxs-lookup"><span data-stu-id="1eab4-102">Any function</span></span>

<span data-ttu-id="1eab4-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1eab4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1eab4-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1eab4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1eab4-105">配列と、配列の要素に対して定義された述語が指定されている場合、配列の少なくとも1つの要素が述語を満たすかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1eab4-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="1eab4-106">入力</span><span class="sxs-lookup"><span data-stu-id="1eab4-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="1eab4-107">述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1eab4-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1eab4-108">`'T` `Bool` 要素のチェックに使用されるからへの関数。</span><span class="sxs-lookup"><span data-stu-id="1eab4-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="1eab4-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="1eab4-109">array : 'T[]</span></span>

<span data-ttu-id="1eab4-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="1eab4-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1eab4-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1eab4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1eab4-112">`Bool`すべての要素に適用される述語の関数または関数の値。</span><span class="sxs-lookup"><span data-stu-id="1eab4-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1eab4-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="1eab4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1eab4-114">&</span><span class="sxs-lookup"><span data-stu-id="1eab4-114">'T</span></span>

<span data-ttu-id="1eab4-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="1eab4-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="1eab4-116">例</span><span class="sxs-lookup"><span data-stu-id="1eab4-116">Example</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function IsThreePresent() : Bool {
    let arrayOfInts = [1, 2, 3, 4, 5];
    let is3Present = IsNumberPresentInArray(3, arrayOfInts);
    return is3Present;
}

function IsNumberPresentInArray(n : Int, array : Int[]) : Bool {
    return Any(EqualI(_, n), array);
}
```

## <a name="remarks"></a><span data-ttu-id="1eab4-117">解説</span><span class="sxs-lookup"><span data-stu-id="1eab4-117">Remarks</span></span>

<span data-ttu-id="1eab4-118">関数は、ジェネリック型に対して定義されます。つまり、配列と関数がある場合は、一部の要素が満たされるかどうか `'T[]` `predicate: 'T -> Bool` `Bool` を示す値を生成でき `predicate` ます。</span><span class="sxs-lookup"><span data-stu-id="1eab4-118">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>