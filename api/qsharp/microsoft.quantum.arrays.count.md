---
uid: Microsoft.Quantum.Arrays.Count
title: Count 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842850"
---
# <a name="count-function"></a><span data-ttu-id="1afb3-102">Count 関数</span><span class="sxs-lookup"><span data-stu-id="1afb3-102">Count function</span></span>

<span data-ttu-id="1afb3-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1afb3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1afb3-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1afb3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1afb3-105">配列と、配列の要素に対して定義された述語を指定すると、は、述語を満たす要素で構成される配列の要素数を返します。</span><span class="sxs-lookup"><span data-stu-id="1afb3-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="1afb3-106">入力</span><span class="sxs-lookup"><span data-stu-id="1afb3-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="1afb3-107">述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1afb3-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1afb3-108">`'T`要素をフィルター処理するために使用されるブール値からブール型への関数。</span><span class="sxs-lookup"><span data-stu-id="1afb3-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="1afb3-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="1afb3-109">array : 'T[]</span></span>

<span data-ttu-id="1afb3-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="1afb3-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="1afb3-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1afb3-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1afb3-112">述語を満たす内の要素の数 `array` 。</span><span class="sxs-lookup"><span data-stu-id="1afb3-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1afb3-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="1afb3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1afb3-114">&</span><span class="sxs-lookup"><span data-stu-id="1afb3-114">'T</span></span>

<span data-ttu-id="1afb3-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="1afb3-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="1afb3-116">例</span><span class="sxs-lookup"><span data-stu-id="1afb3-116">Example</span></span>

<span data-ttu-id="1afb3-117">次のコードは、"Count" 関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="1afb3-117">The following code demonstrates the "Count" function.</span></span>
<span data-ttu-id="1afb3-118">述語は、関数を使用して定義され @"microsoft.quantum.logical.greaterthani" ます。</span><span class="sxs-lookup"><span data-stu-id="1afb3-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a><span data-ttu-id="1afb3-119">解説</span><span class="sxs-lookup"><span data-stu-id="1afb3-119">Remarks</span></span>

<span data-ttu-id="1afb3-120">関数は、ジェネリック型に対して定義されます。つまり、配列と述語がある場合は、 `'T[]` `'T -> Bool` 要素をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="1afb3-120">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>