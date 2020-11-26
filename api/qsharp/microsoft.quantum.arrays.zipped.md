---
uid: Microsoft.Quantum.Arrays.Zipped
title: Zip 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219755"
---
# <a name="zipped-function"></a><span data-ttu-id="90aee-102">Zip 関数</span><span class="sxs-lookup"><span data-stu-id="90aee-102">Zipped function</span></span>

<span data-ttu-id="90aee-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="90aee-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="90aee-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90aee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90aee-105">2つの配列を指定すると、は、各ペアに各元の配列の要素が含まれるように、ペアの新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="90aee-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="90aee-106">入力</span><span class="sxs-lookup"><span data-stu-id="90aee-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="90aee-107">左: \ []</span><span class="sxs-lookup"><span data-stu-id="90aee-107">left : 'T[]</span></span>

<span data-ttu-id="90aee-108">各組の最初の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="90aee-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="90aee-109">right: ' U []</span><span class="sxs-lookup"><span data-stu-id="90aee-109">right : 'U[]</span></span>

<span data-ttu-id="90aee-110">各組の2番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="90aee-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="90aee-111">出力: (' U '、' U) []</span><span class="sxs-lookup"><span data-stu-id="90aee-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="90aee-112">各のフォームのペアを格納 `(left[idx], right[idx])` している配列 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="90aee-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="90aee-113">2つの配列が等しくない場合、出力は入力の短い方の長さになります。</span><span class="sxs-lookup"><span data-stu-id="90aee-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="90aee-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="90aee-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="90aee-115">&</span><span class="sxs-lookup"><span data-stu-id="90aee-115">'T</span></span>

<span data-ttu-id="90aee-116">左の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="90aee-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="90aee-117">' U</span><span class="sxs-lookup"><span data-stu-id="90aee-117">'U</span></span>

<span data-ttu-id="90aee-118">正しい配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="90aee-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="90aee-119">参照</span><span class="sxs-lookup"><span data-stu-id="90aee-119">See Also</span></span>

- [<span data-ttu-id="90aee-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="90aee-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="90aee-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="90aee-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="90aee-122">Microsoft.................</span><span class="sxs-lookup"><span data-stu-id="90aee-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)