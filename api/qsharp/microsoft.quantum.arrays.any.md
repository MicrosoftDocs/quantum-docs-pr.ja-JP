---
uid: Microsoft.Quantum.Arrays.Any
title: すべての関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: 717ab9ebcbb864a6faf1c14cd36125e589849f2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221659"
---
# <a name="any-function"></a><span data-ttu-id="5bfb6-102">すべての関数</span><span class="sxs-lookup"><span data-stu-id="5bfb6-102">Any function</span></span>

<span data-ttu-id="5bfb6-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5bfb6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5bfb6-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5bfb6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5bfb6-105">配列と、配列の要素に対して定義された述語が指定されている場合、配列の少なくとも1つの要素が述語を満たすかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5bfb6-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="5bfb6-106">入力</span><span class="sxs-lookup"><span data-stu-id="5bfb6-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="5bfb6-107">述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5bfb6-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5bfb6-108">`'T` `Bool` 要素のチェックに使用されるからへの関数。</span><span class="sxs-lookup"><span data-stu-id="5bfb6-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="5bfb6-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="5bfb6-109">array : 'T[]</span></span>

<span data-ttu-id="5bfb6-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="5bfb6-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5bfb6-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5bfb6-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5bfb6-112">`Bool`すべての要素に適用される述語の関数または関数の値。</span><span class="sxs-lookup"><span data-stu-id="5bfb6-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5bfb6-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="5bfb6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5bfb6-114">&</span><span class="sxs-lookup"><span data-stu-id="5bfb6-114">'T</span></span>

<span data-ttu-id="5bfb6-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="5bfb6-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="5bfb6-116">解説</span><span class="sxs-lookup"><span data-stu-id="5bfb6-116">Remarks</span></span>

<span data-ttu-id="5bfb6-117">関数は、ジェネリック型に対して定義されます。つまり、配列と関数がある場合は、一部の要素が満たされるかどうか `'T[]` `predicate: 'T -> Bool` `Bool` を示す値を生成でき `predicate` ます。</span><span class="sxs-lookup"><span data-stu-id="5bfb6-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>