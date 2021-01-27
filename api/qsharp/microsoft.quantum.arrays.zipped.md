---
uid: Microsoft.Quantum.Arrays.Zipped
title: Zip 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845346"
---
# <a name="zipped-function"></a><span data-ttu-id="fb666-102">Zip 関数</span><span class="sxs-lookup"><span data-stu-id="fb666-102">Zipped function</span></span>

<span data-ttu-id="fb666-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fb666-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fb666-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb666-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb666-105">2つの配列を指定すると、は、各ペアに各元の配列の要素が含まれるように、ペアの新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="fb666-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="fb666-106">入力</span><span class="sxs-lookup"><span data-stu-id="fb666-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="fb666-107">左: \ []</span><span class="sxs-lookup"><span data-stu-id="fb666-107">left : 'T[]</span></span>

<span data-ttu-id="fb666-108">各組の最初の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="fb666-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="fb666-109">right: ' U []</span><span class="sxs-lookup"><span data-stu-id="fb666-109">right : 'U[]</span></span>

<span data-ttu-id="fb666-110">各組の2番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="fb666-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="fb666-111">出力: (' U '、' U) []</span><span class="sxs-lookup"><span data-stu-id="fb666-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="fb666-112">各のフォームのペアを格納 `(left[idx], right[idx])` している配列 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="fb666-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="fb666-113">2つの配列が等しくない場合、出力は入力の短い方の長さになります。</span><span class="sxs-lookup"><span data-stu-id="fb666-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fb666-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb666-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fb666-115">&</span><span class="sxs-lookup"><span data-stu-id="fb666-115">'T</span></span>

<span data-ttu-id="fb666-116">左の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="fb666-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="fb666-117">' U</span><span class="sxs-lookup"><span data-stu-id="fb666-117">'U</span></span>

<span data-ttu-id="fb666-118">正しい配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="fb666-118">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="fb666-119">例</span><span class="sxs-lookup"><span data-stu-id="fb666-119">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="fb666-120">参照</span><span class="sxs-lookup"><span data-stu-id="fb666-120">See Also</span></span>

- [<span data-ttu-id="fb666-121">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="fb666-121">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="fb666-122">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="fb666-122">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="fb666-123">Microsoft.................</span><span class="sxs-lookup"><span data-stu-id="fb666-123">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)