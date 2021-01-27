---
uid: Microsoft.Quantum.Arrays.All
title: All 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 17e61ea161b90fe089b7df7c10188d604d72dcfa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842893"
---
# <a name="all-function"></a><span data-ttu-id="d060b-102">All 関数</span><span class="sxs-lookup"><span data-stu-id="d060b-102">All function</span></span>

<span data-ttu-id="d060b-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d060b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d060b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d060b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d060b-105">配列と、配列の要素に対して定義されている述語が指定されている場合、配列のすべての要素が述語を満たすかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d060b-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="d060b-106">入力</span><span class="sxs-lookup"><span data-stu-id="d060b-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="d060b-107">述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d060b-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d060b-108">`'T` `Bool` 要素のチェックに使用されるからへの関数。</span><span class="sxs-lookup"><span data-stu-id="d060b-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="d060b-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="d060b-109">array : 'T[]</span></span>

<span data-ttu-id="d060b-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="d060b-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d060b-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d060b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d060b-112">`Bool`すべての要素に適用される述語の関数と関数の値。</span><span class="sxs-lookup"><span data-stu-id="d060b-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d060b-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="d060b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d060b-114">&</span><span class="sxs-lookup"><span data-stu-id="d060b-114">'T</span></span>

<span data-ttu-id="d060b-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="d060b-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="d060b-116">例</span><span class="sxs-lookup"><span data-stu-id="d060b-116">Example</span></span>

<span data-ttu-id="d060b-117">次のコードでは、配列のすべての要素が0以外であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d060b-117">The following code checks whether all elements of the array are non-zero:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function AllDemo() : Unit {
    let predicate = NotEqualI(_, 0);
    let isNonZero = All(predicate, [2, 3, 4, 5, 6, 0]);
    Message($"{isNonZero}");
}
```

## <a name="remarks"></a><span data-ttu-id="d060b-118">解説</span><span class="sxs-lookup"><span data-stu-id="d060b-118">Remarks</span></span>

<span data-ttu-id="d060b-119">関数は、ジェネリック型に対して定義されます。つまり、配列と関数がある場合は常に、 `'T[]` `predicate: 'T -> Bool` すべての要素が `Bool` 満たされるかどうかを示す値を生成でき `predicate` ます。</span><span class="sxs-lookup"><span data-stu-id="d060b-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>