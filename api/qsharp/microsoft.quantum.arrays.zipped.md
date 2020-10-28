---
uid: Microsoft.Quantum.Arrays.Zipped
title: Zip 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718711"
---
# <a name="zipped-function"></a><span data-ttu-id="ac80f-102">Zip 関数</span><span class="sxs-lookup"><span data-stu-id="ac80f-102">Zipped function</span></span>

<span data-ttu-id="ac80f-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ac80f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ac80f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ac80f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ac80f-105">2つの配列を指定すると、は、各ペアに各元の配列の要素が含まれるように、ペアの新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="ac80f-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="ac80f-106">入力</span><span class="sxs-lookup"><span data-stu-id="ac80f-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="ac80f-107">左: \ []</span><span class="sxs-lookup"><span data-stu-id="ac80f-107">left : 'T[]</span></span>

<span data-ttu-id="ac80f-108">各組の最初の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="ac80f-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="ac80f-109">right: ' U []</span><span class="sxs-lookup"><span data-stu-id="ac80f-109">right : 'U[]</span></span>

<span data-ttu-id="ac80f-110">各組の2番目の要素の値を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="ac80f-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="ac80f-111">出力: (' U '、' U) []</span><span class="sxs-lookup"><span data-stu-id="ac80f-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="ac80f-112">各のフォームのペアを格納 `(left[idx], right[idx])` している配列 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="ac80f-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="ac80f-113">2つの配列が等しくない場合、出力は入力の短い方の長さになります。</span><span class="sxs-lookup"><span data-stu-id="ac80f-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ac80f-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="ac80f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ac80f-115">&</span><span class="sxs-lookup"><span data-stu-id="ac80f-115">'T</span></span>

<span data-ttu-id="ac80f-116">左の配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="ac80f-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="ac80f-117">' U</span><span class="sxs-lookup"><span data-stu-id="ac80f-117">'U</span></span>

<span data-ttu-id="ac80f-118">正しい配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="ac80f-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac80f-119">参照</span><span class="sxs-lookup"><span data-stu-id="ac80f-119">See Also</span></span>

- [<span data-ttu-id="ac80f-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="ac80f-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="ac80f-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="ac80f-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="ac80f-122">Microsoft.................</span><span class="sxs-lookup"><span data-stu-id="ac80f-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)