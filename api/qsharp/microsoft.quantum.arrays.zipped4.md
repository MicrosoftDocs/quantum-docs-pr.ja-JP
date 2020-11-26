---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d5ee10ac9776383e75bc16a5c003a8b1a65c5698
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219636"
---
# <a name="zipped4-function"></a><span data-ttu-id="9eaa9-102">Zipped4 関数</span><span class="sxs-lookup"><span data-stu-id="9eaa9-102">Zipped4 function</span></span>

<span data-ttu-id="9eaa9-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9eaa9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9eaa9-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9eaa9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9eaa9-105">4つの配列がある場合、4組の新しい配列を返して、各4組に各元の配列の要素が格納されるようにします。</span><span class="sxs-lookup"><span data-stu-id="9eaa9-105">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="9eaa9-106">入力</span><span class="sxs-lookup"><span data-stu-id="9eaa9-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="9eaa9-107">1: 1 []</span><span class="sxs-lookup"><span data-stu-id="9eaa9-107">first : 'T1[]</span></span>

<span data-ttu-id="9eaa9-108">各組の最初の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="9eaa9-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="9eaa9-109">2番目: t 2 []</span><span class="sxs-lookup"><span data-stu-id="9eaa9-109">second : 'T2[]</span></span>

<span data-ttu-id="9eaa9-110">各組の2番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="9eaa9-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="9eaa9-111">3番目: t 3 []</span><span class="sxs-lookup"><span data-stu-id="9eaa9-111">third : 'T3[]</span></span>

<span data-ttu-id="9eaa9-112">各組の3番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="9eaa9-112">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="9eaa9-113">4番目: t 4 []</span><span class="sxs-lookup"><span data-stu-id="9eaa9-113">fourth : 'T4[]</span></span>

<span data-ttu-id="9eaa9-114">各組の4番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="9eaa9-114">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="9eaa9-115">出力: (1、2、t 3、t 4) []</span><span class="sxs-lookup"><span data-stu-id="9eaa9-115">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="9eaa9-116">それぞれの形式の4組のを格納 `(first[idx], second[idx], third[idx], fourth[idx])` している配列 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="9eaa9-116">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="9eaa9-117">4つの配列の長さが等しくない場合、出力は入力の短い方の長さになります。</span><span class="sxs-lookup"><span data-stu-id="9eaa9-117">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9eaa9-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="9eaa9-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="9eaa9-119">1</span><span class="sxs-lookup"><span data-stu-id="9eaa9-119">'T1</span></span>

<span data-ttu-id="9eaa9-120">最初の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="9eaa9-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="9eaa9-121">T 2</span><span class="sxs-lookup"><span data-stu-id="9eaa9-121">'T2</span></span>

<span data-ttu-id="9eaa9-122">2番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="9eaa9-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="9eaa9-123">T 3</span><span class="sxs-lookup"><span data-stu-id="9eaa9-123">'T3</span></span>

<span data-ttu-id="9eaa9-124">3番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="9eaa9-124">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="9eaa9-125">T 4</span><span class="sxs-lookup"><span data-stu-id="9eaa9-125">'T4</span></span>

<span data-ttu-id="9eaa9-126">4番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="9eaa9-126">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="9eaa9-127">参照</span><span class="sxs-lookup"><span data-stu-id="9eaa9-127">See Also</span></span>

- [<span data-ttu-id="9eaa9-128">Microsoft.Quantum.Arrays.Zip中</span><span class="sxs-lookup"><span data-stu-id="9eaa9-128">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="9eaa9-129">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="9eaa9-129">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)