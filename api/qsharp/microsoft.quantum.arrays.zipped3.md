---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: 37fda4082a46870270414649f807659fa561962b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219687"
---
# <a name="zipped3-function"></a><span data-ttu-id="35f36-102">Zipped3 関数</span><span class="sxs-lookup"><span data-stu-id="35f36-102">Zipped3 function</span></span>

<span data-ttu-id="35f36-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="35f36-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="35f36-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35f36-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35f36-105">3つの配列を指定すると、3組の新しい配列が返されます。これにより、各3組には各元の配列の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="35f36-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="35f36-106">入力</span><span class="sxs-lookup"><span data-stu-id="35f36-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="35f36-107">1: 1 []</span><span class="sxs-lookup"><span data-stu-id="35f36-107">first : 'T1[]</span></span>

<span data-ttu-id="35f36-108">各組の最初の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="35f36-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="35f36-109">2番目: t 2 []</span><span class="sxs-lookup"><span data-stu-id="35f36-109">second : 'T2[]</span></span>

<span data-ttu-id="35f36-110">各組の2番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="35f36-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="35f36-111">3番目: t 3 []</span><span class="sxs-lookup"><span data-stu-id="35f36-111">third : 'T3[]</span></span>

<span data-ttu-id="35f36-112">各組の3番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="35f36-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="35f36-113">出力: (1、2、t 3) []</span><span class="sxs-lookup"><span data-stu-id="35f36-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="35f36-114">各のフォームの3組のタプルを格納 `(first[idx], second[idx], third[idx])` している配列 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="35f36-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="35f36-115">3つの配列の長さが等しくない場合、出力は入力の短い方の長さになります。</span><span class="sxs-lookup"><span data-stu-id="35f36-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="35f36-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="35f36-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="35f36-117">1</span><span class="sxs-lookup"><span data-stu-id="35f36-117">'T1</span></span>

<span data-ttu-id="35f36-118">最初の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="35f36-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="35f36-119">T 2</span><span class="sxs-lookup"><span data-stu-id="35f36-119">'T2</span></span>

<span data-ttu-id="35f36-120">2番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="35f36-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="35f36-121">T 3</span><span class="sxs-lookup"><span data-stu-id="35f36-121">'T3</span></span>

<span data-ttu-id="35f36-122">3番目の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="35f36-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="35f36-123">参照</span><span class="sxs-lookup"><span data-stu-id="35f36-123">See Also</span></span>

- [<span data-ttu-id="35f36-124">Microsoft.Quantum.Arrays.Zip中</span><span class="sxs-lookup"><span data-stu-id="35f36-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="35f36-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="35f36-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)