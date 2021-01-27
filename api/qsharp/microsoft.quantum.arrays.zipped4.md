---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: e932cd4c266b39a3a88da48e649448d0028f61e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845328"
---
# <a name="zipped4-function"></a><span data-ttu-id="868ab-102">Zipped4 関数</span><span class="sxs-lookup"><span data-stu-id="868ab-102">Zipped4 function</span></span>

<span data-ttu-id="868ab-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="868ab-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="868ab-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="868ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="868ab-105">4つの配列がある場合、4組の新しい配列を返して、各4組に各元の配列の要素が格納されるようにします。</span><span class="sxs-lookup"><span data-stu-id="868ab-105">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="868ab-106">入力</span><span class="sxs-lookup"><span data-stu-id="868ab-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="868ab-107">1: 1 []</span><span class="sxs-lookup"><span data-stu-id="868ab-107">first : 'T1[]</span></span>

<span data-ttu-id="868ab-108">各組の最初の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="868ab-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="868ab-109">2番目: t 2 []</span><span class="sxs-lookup"><span data-stu-id="868ab-109">second : 'T2[]</span></span>

<span data-ttu-id="868ab-110">各組の2番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="868ab-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="868ab-111">3番目: t 3 []</span><span class="sxs-lookup"><span data-stu-id="868ab-111">third : 'T3[]</span></span>

<span data-ttu-id="868ab-112">各組の3番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="868ab-112">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="868ab-113">4番目: t 4 []</span><span class="sxs-lookup"><span data-stu-id="868ab-113">fourth : 'T4[]</span></span>

<span data-ttu-id="868ab-114">各組の4番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="868ab-114">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="868ab-115">出力: (1、2、t 3、t 4) []</span><span class="sxs-lookup"><span data-stu-id="868ab-115">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="868ab-116">それぞれの形式の4組のを格納 `(first[idx], second[idx], third[idx], fourth[idx])` している配列 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="868ab-116">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="868ab-117">4つの配列の長さが等しくない場合、出力は入力の短い方の長さになります。</span><span class="sxs-lookup"><span data-stu-id="868ab-117">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="868ab-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="868ab-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="868ab-119">1</span><span class="sxs-lookup"><span data-stu-id="868ab-119">'T1</span></span>

<span data-ttu-id="868ab-120">最初の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="868ab-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="868ab-121">T 2</span><span class="sxs-lookup"><span data-stu-id="868ab-121">'T2</span></span>

<span data-ttu-id="868ab-122">2番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="868ab-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="868ab-123">T 3</span><span class="sxs-lookup"><span data-stu-id="868ab-123">'T3</span></span>

<span data-ttu-id="868ab-124">3番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="868ab-124">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="868ab-125">T 4</span><span class="sxs-lookup"><span data-stu-id="868ab-125">'T4</span></span>

<span data-ttu-id="868ab-126">4番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="868ab-126">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="868ab-127">参照</span><span class="sxs-lookup"><span data-stu-id="868ab-127">See Also</span></span>

- [<span data-ttu-id="868ab-128">Microsoft.Quantum.Arrays.Zip中</span><span class="sxs-lookup"><span data-stu-id="868ab-128">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="868ab-129">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="868ab-129">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)