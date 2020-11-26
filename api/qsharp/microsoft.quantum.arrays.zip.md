---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 44db8d38d96babd16ead5ae6dde91da23bdee2c9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219857"
---
# <a name="zip-function"></a><span data-ttu-id="8805c-102">Zip 関数</span><span class="sxs-lookup"><span data-stu-id="8805c-102">Zip function</span></span>

<span data-ttu-id="8805c-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8805c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8805c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8805c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="8805c-105">Zip は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="8805c-105">Zip has been deprecated.</span></span> <span data-ttu-id="8805c-106">代わりに、<xref:Microsoft.Quantum.Arrays.Zipped> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="8805c-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="8805c-107">2つの配列を指定すると、は、各ペアに各元の配列の要素が含まれるように、ペアの新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="8805c-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="8805c-108">入力</span><span class="sxs-lookup"><span data-stu-id="8805c-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="8805c-109">左: \ []</span><span class="sxs-lookup"><span data-stu-id="8805c-109">left : 'T[]</span></span>

<span data-ttu-id="8805c-110">各組の最初の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="8805c-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="8805c-111">right: ' U []</span><span class="sxs-lookup"><span data-stu-id="8805c-111">right : 'U[]</span></span>

<span data-ttu-id="8805c-112">各組の2番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="8805c-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="8805c-113">出力: (' U '、' U) []</span><span class="sxs-lookup"><span data-stu-id="8805c-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="8805c-114">各のフォームのペアを格納 `(left[idx], right[idx])` している配列 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="8805c-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="8805c-115">2つの配列が等しくない場合、出力は入力の短い方の長さになります。</span><span class="sxs-lookup"><span data-stu-id="8805c-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8805c-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="8805c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8805c-117">&</span><span class="sxs-lookup"><span data-stu-id="8805c-117">'T</span></span>

<span data-ttu-id="8805c-118">左の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="8805c-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="8805c-119">' U</span><span class="sxs-lookup"><span data-stu-id="8805c-119">'U</span></span>

<span data-ttu-id="8805c-120">正しい配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="8805c-120">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="8805c-121">参照</span><span class="sxs-lookup"><span data-stu-id="8805c-121">See Also</span></span>

- [<span data-ttu-id="8805c-122">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="8805c-122">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="8805c-123">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="8805c-123">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="8805c-124">Microsoft.................</span><span class="sxs-lookup"><span data-stu-id="8805c-124">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)