---
uid: Microsoft.Quantum.Arrays.Zip3
title: Array.zip3 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: a6e7519755c4d473f6ba255ac5f877b2a3894d71
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219823"
---
# <a name="zip3-function"></a><span data-ttu-id="d62d7-102">Array.zip3 関数</span><span class="sxs-lookup"><span data-stu-id="d62d7-102">Zip3 function</span></span>

<span data-ttu-id="d62d7-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d62d7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d62d7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d62d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="d62d7-105">Array.zip3 は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="d62d7-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="d62d7-106">代わりに、<xref:Microsoft.Quantum.Arrays.Zipped3> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="d62d7-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="d62d7-107">3つの配列を指定すると、3組の新しい配列が返されます。これにより、各3組には各元の配列の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d62d7-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="d62d7-108">入力</span><span class="sxs-lookup"><span data-stu-id="d62d7-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="d62d7-109">1: 1 []</span><span class="sxs-lookup"><span data-stu-id="d62d7-109">first : 'T1[]</span></span>

<span data-ttu-id="d62d7-110">各組の最初の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="d62d7-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="d62d7-111">2番目: t 2 []</span><span class="sxs-lookup"><span data-stu-id="d62d7-111">second : 'T2[]</span></span>

<span data-ttu-id="d62d7-112">各組の2番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="d62d7-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="d62d7-113">3番目: t 3 []</span><span class="sxs-lookup"><span data-stu-id="d62d7-113">third : 'T3[]</span></span>

<span data-ttu-id="d62d7-114">各組の3番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="d62d7-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="d62d7-115">出力: (1、2、t 3) []</span><span class="sxs-lookup"><span data-stu-id="d62d7-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="d62d7-116">各のフォームの3組のタプルを格納 `(first[idx], second[idx], third[idx])` している配列 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="d62d7-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="d62d7-117">3つの配列の長さが等しくない場合、出力は入力の短い方の長さになります。</span><span class="sxs-lookup"><span data-stu-id="d62d7-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d62d7-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="d62d7-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="d62d7-119">1</span><span class="sxs-lookup"><span data-stu-id="d62d7-119">'T1</span></span>

<span data-ttu-id="d62d7-120">最初の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="d62d7-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="d62d7-121">T 2</span><span class="sxs-lookup"><span data-stu-id="d62d7-121">'T2</span></span>

<span data-ttu-id="d62d7-122">2番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="d62d7-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="d62d7-123">T 3</span><span class="sxs-lookup"><span data-stu-id="d62d7-123">'T3</span></span>

<span data-ttu-id="d62d7-124">3番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="d62d7-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="d62d7-125">参照</span><span class="sxs-lookup"><span data-stu-id="d62d7-125">See Also</span></span>

- [<span data-ttu-id="d62d7-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="d62d7-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="d62d7-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="d62d7-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)