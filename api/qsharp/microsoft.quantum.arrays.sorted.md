---
uid: Microsoft.Quantum.Arrays.Sorted
title: Sorted 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845442"
---
# <a name="sorted-function"></a><span data-ttu-id="03547-102">Sorted 関数</span><span class="sxs-lookup"><span data-stu-id="03547-102">Sorted function</span></span>

<span data-ttu-id="03547-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="03547-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="03547-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03547-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03547-105">配列が指定された場合、は、指定された比較関数によって並べ替えられた配列の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="03547-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="03547-106">入力</span><span class="sxs-lookup"><span data-stu-id="03547-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="03547-107">比較: (' t, ' t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="03547-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="03547-108">`a` `b` がの場合に、以下の2つの要素を比較する関数 `comparison(a, b)` `true` 。</span><span class="sxs-lookup"><span data-stu-id="03547-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="03547-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="03547-109">array : 'T[]</span></span>

<span data-ttu-id="03547-110">並べ替える配列。</span><span class="sxs-lookup"><span data-stu-id="03547-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="03547-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="03547-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="03547-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="03547-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="03547-113">&</span><span class="sxs-lookup"><span data-stu-id="03547-113">'T</span></span>

<span data-ttu-id="03547-114">の各要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="03547-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="03547-115">例</span><span class="sxs-lookup"><span data-stu-id="03547-115">Example</span></span>

<span data-ttu-id="03547-116">次のスニペットは、整数の配列を昇順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="03547-116">The following snippet sorts an array of integers to occur in ascending order:</span></span>

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a><span data-ttu-id="03547-117">解説</span><span class="sxs-lookup"><span data-stu-id="03547-117">Remarks</span></span>

<span data-ttu-id="03547-118">関数は `comparison` 推移的であると見なされ、 `comparison(a, b)` との場合はと `comparison(b, c)` 見なされ `comparison(a, c)` ます。</span><span class="sxs-lookup"><span data-stu-id="03547-118">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="03547-119">このプロパティがを保持していない場合、この関数の出力は正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="03547-119">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="03547-120">これは関数であるため、2つの要素が等しいと見なされた場合、つまり `comparison` `comparison(a, b)` とが `comparison(b, a)` 両方とも等しい場合でも、結果は完全に解釈され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="03547-120">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="03547-121">特に、この関数によって実行される並べ替えは安定していることが保証されているので、2つの要素 `a` とが `b` 内で同じ順序で発生し、かつがの下に等しいと見なされると `array` `comparison` 、 `a` は出力の前にも表示され `b` ます。</span><span class="sxs-lookup"><span data-stu-id="03547-121">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="03547-122">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="03547-122">For example:</span></span>

```qsharp
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```