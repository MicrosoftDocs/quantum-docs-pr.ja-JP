---
uid: Microsoft.Quantum.Arrays.Zip3
title: Array.zip3 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: f4b1a769614ee9434b2141b8fcb91f34cd071bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718723"
---
# <a name="zip3-function"></a><span data-ttu-id="40156-102">Array.zip3 関数</span><span class="sxs-lookup"><span data-stu-id="40156-102">Zip3 function</span></span>

<span data-ttu-id="40156-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="40156-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="40156-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="40156-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="40156-105">Array.zip3 は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="40156-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="40156-106">代わりに、<xref:Microsoft.Quantum.Arrays.Zipped3> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="40156-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="40156-107">3つの配列を指定すると、3組の新しい配列が返されます。これにより、各3組には各元の配列の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="40156-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="40156-108">入力</span><span class="sxs-lookup"><span data-stu-id="40156-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="40156-109">1: 1 []</span><span class="sxs-lookup"><span data-stu-id="40156-109">first : 'T1[]</span></span>

<span data-ttu-id="40156-110">各組の最初の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="40156-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="40156-111">2番目: t 2 []</span><span class="sxs-lookup"><span data-stu-id="40156-111">second : 'T2[]</span></span>

<span data-ttu-id="40156-112">各組の2番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="40156-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="40156-113">3番目: t 3 []</span><span class="sxs-lookup"><span data-stu-id="40156-113">third : 'T3[]</span></span>

<span data-ttu-id="40156-114">各組の3番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="40156-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="40156-115">出力: (1、2、t 3) []</span><span class="sxs-lookup"><span data-stu-id="40156-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="40156-116">各のフォームの3組のタプルを格納 `(first[idx], second[idx], third[idx])` している配列 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="40156-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="40156-117">3つの配列の長さが等しくない場合、出力は入力の短い方の長さになります。</span><span class="sxs-lookup"><span data-stu-id="40156-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="40156-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="40156-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="40156-119">1</span><span class="sxs-lookup"><span data-stu-id="40156-119">'T1</span></span>

<span data-ttu-id="40156-120">最初の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="40156-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="40156-121">T 2</span><span class="sxs-lookup"><span data-stu-id="40156-121">'T2</span></span>

<span data-ttu-id="40156-122">2番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="40156-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="40156-123">T 3</span><span class="sxs-lookup"><span data-stu-id="40156-123">'T3</span></span>

<span data-ttu-id="40156-124">3番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="40156-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="40156-125">参照</span><span class="sxs-lookup"><span data-stu-id="40156-125">See Also</span></span>

- [<span data-ttu-id="40156-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="40156-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="40156-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="40156-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)