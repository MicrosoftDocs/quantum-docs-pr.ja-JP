---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: 330c1f789585f64cf255bc74f8a9c1ccf81b009e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719102"
---
# <a name="issorted-function"></a><span data-ttu-id="7587a-102">IsSorted 関数</span><span class="sxs-lookup"><span data-stu-id="7587a-102">IsSorted function</span></span>

<span data-ttu-id="7587a-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7587a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7587a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7587a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7587a-105">配列が指定されている場合、指定された比較関数によって定義されたとおりに配列が並べ替えられるかどうかを返します。</span><span class="sxs-lookup"><span data-stu-id="7587a-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="7587a-106">入力</span><span class="sxs-lookup"><span data-stu-id="7587a-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="7587a-107">比較: (' t, ' t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7587a-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7587a-108">`a` `b` がの場合に、以下の2つの要素を比較する関数 `comparison(a, b)` `true` 。</span><span class="sxs-lookup"><span data-stu-id="7587a-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="7587a-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="7587a-109">array : 'T[]</span></span>

<span data-ttu-id="7587a-110">チェックする配列。</span><span class="sxs-lookup"><span data-stu-id="7587a-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7587a-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7587a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7587a-112">`true` 要素の各ペアと、その順序で発生する場合にのみ `a` `b` `array` 、 `comparison(a, b)` はに `true` なります。</span><span class="sxs-lookup"><span data-stu-id="7587a-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7587a-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="7587a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7587a-114">&</span><span class="sxs-lookup"><span data-stu-id="7587a-114">'T</span></span>

<span data-ttu-id="7587a-115">の各要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="7587a-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7587a-116">解説</span><span class="sxs-lookup"><span data-stu-id="7587a-116">Remarks</span></span>

<span data-ttu-id="7587a-117">関数は `comparison` 推移的であると見なされ、 `comparison(a, b)` との場合はと `comparison(b, c)` 見なされ `comparison(a, c)` ます。</span><span class="sxs-lookup"><span data-stu-id="7587a-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="7587a-118">このプロパティがを保持していない場合、この関数の出力は正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7587a-118">If this property does not hold, then the output of this function may be incorrect.</span></span>