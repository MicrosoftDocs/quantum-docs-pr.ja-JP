---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d42b3b6db059163f6c766d4f133551be293c153d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718699"
---
# <a name="zip4-function"></a><span data-ttu-id="ff4ce-102">Zip4 関数</span><span class="sxs-lookup"><span data-stu-id="ff4ce-102">Zip4 function</span></span>

<span data-ttu-id="ff4ce-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ff4ce-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ff4ce-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff4ce-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="ff4ce-105">Zip4 は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="ff4ce-105">Zip4 has been deprecated.</span></span> <span data-ttu-id="ff4ce-106">代わりに、<xref:Microsoft.Quantum.Arrays.Zipped4> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="ff4ce-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.</span></span>

<span data-ttu-id="ff4ce-107">4つの配列がある場合、4組の新しい配列を返して、各4組に各元の配列の要素が格納されるようにします。</span><span class="sxs-lookup"><span data-stu-id="ff4ce-107">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="ff4ce-108">入力</span><span class="sxs-lookup"><span data-stu-id="ff4ce-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="ff4ce-109">1: 1 []</span><span class="sxs-lookup"><span data-stu-id="ff4ce-109">first : 'T1[]</span></span>

<span data-ttu-id="ff4ce-110">各組の最初の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="ff4ce-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="ff4ce-111">2番目: t 2 []</span><span class="sxs-lookup"><span data-stu-id="ff4ce-111">second : 'T2[]</span></span>

<span data-ttu-id="ff4ce-112">各組の2番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="ff4ce-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="ff4ce-113">3番目: t 3 []</span><span class="sxs-lookup"><span data-stu-id="ff4ce-113">third : 'T3[]</span></span>

<span data-ttu-id="ff4ce-114">各組の3番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="ff4ce-114">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="ff4ce-115">4番目: t 4 []</span><span class="sxs-lookup"><span data-stu-id="ff4ce-115">fourth : 'T4[]</span></span>

<span data-ttu-id="ff4ce-116">各組の4番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="ff4ce-116">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="ff4ce-117">出力: (1、2、t 3、t 4) []</span><span class="sxs-lookup"><span data-stu-id="ff4ce-117">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="ff4ce-118">それぞれの形式の4組のを格納 `(first[idx], second[idx], third[idx], fourth[idx])` している配列 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="ff4ce-118">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="ff4ce-119">4つの配列の長さが等しくない場合、出力は入力の短い方の長さになります。</span><span class="sxs-lookup"><span data-stu-id="ff4ce-119">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ff4ce-120">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="ff4ce-120">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="ff4ce-121">1</span><span class="sxs-lookup"><span data-stu-id="ff4ce-121">'T1</span></span>

<span data-ttu-id="ff4ce-122">最初の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="ff4ce-122">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="ff4ce-123">T 2</span><span class="sxs-lookup"><span data-stu-id="ff4ce-123">'T2</span></span>

<span data-ttu-id="ff4ce-124">2番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="ff4ce-124">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="ff4ce-125">T 3</span><span class="sxs-lookup"><span data-stu-id="ff4ce-125">'T3</span></span>

<span data-ttu-id="ff4ce-126">3番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="ff4ce-126">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="ff4ce-127">T 4</span><span class="sxs-lookup"><span data-stu-id="ff4ce-127">'T4</span></span>

<span data-ttu-id="ff4ce-128">4番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="ff4ce-128">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff4ce-129">参照</span><span class="sxs-lookup"><span data-stu-id="ff4ce-129">See Also</span></span>

- [<span data-ttu-id="ff4ce-130">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="ff4ce-130">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="ff4ce-131">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="ff4ce-131">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)