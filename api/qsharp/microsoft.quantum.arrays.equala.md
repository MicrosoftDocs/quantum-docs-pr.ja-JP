---
uid: Microsoft.Quantum.Arrays.EqualA
title: EqualA 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848690"
---
# <a name="equala-function"></a><span data-ttu-id="57ef7-102">EqualA 関数</span><span class="sxs-lookup"><span data-stu-id="57ef7-102">EqualA function</span></span>

<span data-ttu-id="57ef7-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="57ef7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="57ef7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57ef7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57ef7-105">同じ型の2つの配列と、配列の要素のペアに対して定義されている述語を指定すると、配列が等しいかどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="57ef7-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="57ef7-106">入力</span><span class="sxs-lookup"><span data-stu-id="57ef7-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="57ef7-107">equal: (t, t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="57ef7-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="57ef7-108">`('T, 'T)` `Bool` 配列の2つの要素が等しいかどうかを確認するために使用されるタプルから関数。</span><span class="sxs-lookup"><span data-stu-id="57ef7-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="57ef7-109">配列 1: t []</span><span class="sxs-lookup"><span data-stu-id="57ef7-109">array1 : 'T[]</span></span>

<span data-ttu-id="57ef7-110">比較する最初の配列。</span><span class="sxs-lookup"><span data-stu-id="57ef7-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="57ef7-111">配列名: ' t []</span><span class="sxs-lookup"><span data-stu-id="57ef7-111">array2 : 'T[]</span></span>

<span data-ttu-id="57ef7-112">比較する2番目の配列。</span><span class="sxs-lookup"><span data-stu-id="57ef7-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="57ef7-113">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="57ef7-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="57ef7-114">`true`とが等しい場合にのみ、値を指定し `array1` `array2` ます。</span><span class="sxs-lookup"><span data-stu-id="57ef7-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="57ef7-115">つまり、両方の配列の長さが同じで、すべての要素がで定義されたとおりに等しい場合です `equal` 。</span><span class="sxs-lookup"><span data-stu-id="57ef7-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="57ef7-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="57ef7-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="57ef7-117">&</span><span class="sxs-lookup"><span data-stu-id="57ef7-117">'T</span></span>

<span data-ttu-id="57ef7-118">各配列の要素の型。</span><span class="sxs-lookup"><span data-stu-id="57ef7-118">The type of each array's elements.</span></span>

## <a name="example"></a><span data-ttu-id="57ef7-119">例</span><span class="sxs-lookup"><span data-stu-id="57ef7-119">Example</span></span>

<span data-ttu-id="57ef7-120">次のコードは、配列の異なるペアが等しいかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="57ef7-120">The following code checks whether different pairs of arrays are equal:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a><span data-ttu-id="57ef7-121">解説</span><span class="sxs-lookup"><span data-stu-id="57ef7-121">Remarks</span></span>

<span data-ttu-id="57ef7-122">この関数は、ジェネリック型に対して定義されています。つまり、2つの配列と関数がある場合、 `'T[]` `equal: ('T, 'T) -> Bool` この関数は、 `Bool` 配列が等しいかどうかを示す値を返します。</span><span class="sxs-lookup"><span data-stu-id="57ef7-122">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="57ef7-123">2つの配列が等しいと見なされるには、長さが同じで、配列内の同じ位置にある要素が等しい必要があります。</span><span class="sxs-lookup"><span data-stu-id="57ef7-123">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>