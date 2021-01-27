---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: de8179ab6e835d08e7f41287f31a876b7ecc91c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814382"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="e635f-102">LexographicComparison 関数</span><span class="sxs-lookup"><span data-stu-id="e635f-102">LexographicComparison function</span></span>

<span data-ttu-id="e635f-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e635f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e635f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e635f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e635f-105">比較関数を指定した場合は、lexographically が2つの配列を比較する新しい関数を返します。</span><span class="sxs-lookup"><span data-stu-id="e635f-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="e635f-106">入力</span><span class="sxs-lookup"><span data-stu-id="e635f-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="e635f-107">elementComparison: (' t, ' t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e635f-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e635f-108">との2つの要素を比較し、 `x` `y` が以下の場合にを返す関数 `x` `y` 。</span><span class="sxs-lookup"><span data-stu-id="e635f-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="e635f-109">出力: (' t [], ' t [])-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e635f-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e635f-110">との2つの配列を比較 `xs` `ys` し、 `xs` `ys` lexographical 順序でのの前後にが発生した場合にを返す関数。</span><span class="sxs-lookup"><span data-stu-id="e635f-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e635f-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e635f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e635f-112">&</span><span class="sxs-lookup"><span data-stu-id="e635f-112">'T</span></span>

<span data-ttu-id="e635f-113">比較対象の配列の要素の型。</span><span class="sxs-lookup"><span data-stu-id="e635f-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="e635f-114">解説</span><span class="sxs-lookup"><span data-stu-id="e635f-114">Remarks</span></span>

<span data-ttu-id="e635f-115">2つの配列間の lexographic 比較 `xs` `ys` は、次の手順で定義します。</span><span class="sxs-lookup"><span data-stu-id="e635f-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="e635f-116">とは2つの要素であり `x` `y` `elementComparison(x, y)` 、との `elementComparison(y, x)` 両方が true の場合は等価です。</span><span class="sxs-lookup"><span data-stu-id="e635f-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="e635f-117">両方の配列は、等価でない要素の最初のペアまで、要素ごとに比較されます。</span><span class="sxs-lookup"><span data-stu-id="e635f-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="e635f-118">に従って最初に発生する要素を含む配列 `elementComparison` は、lexographical の順序で最初に発生すると言います。</span><span class="sxs-lookup"><span data-stu-id="e635f-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="e635f-119">等価でない要素が見つからず、一方の配列が他方よりも長い場合、短い方の配列が最初に出現すると言われます。</span><span class="sxs-lookup"><span data-stu-id="e635f-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="e635f-120">参照</span><span class="sxs-lookup"><span data-stu-id="e635f-120">See Also</span></span>

- [<span data-ttu-id="e635f-121">Microsoft... array. Sorted</span><span class="sxs-lookup"><span data-stu-id="e635f-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)