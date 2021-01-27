---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: ElementsAt 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: 295aa4e2d79857405186b835d9788f59db83d1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842791"
---
# <a name="elementsat-function"></a><span data-ttu-id="eb563-102">ElementsAt 関数</span><span class="sxs-lookup"><span data-stu-id="eb563-102">ElementsAt function</span></span>

<span data-ttu-id="eb563-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="eb563-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="eb563-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb563-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb563-105">指定されたインデックスの範囲で配列の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="eb563-105">Returns the array's elements at a given range of indices.</span></span>

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="eb563-106">入力</span><span class="sxs-lookup"><span data-stu-id="eb563-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="eb563-107">範囲: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="eb563-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="eb563-108">配列インデックスの範囲</span><span class="sxs-lookup"><span data-stu-id="eb563-108">Range of array indexes</span></span>


### <a name="array--t"></a><span data-ttu-id="eb563-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="eb563-109">array : 'T[]</span></span>

<span data-ttu-id="eb563-110">Array</span><span class="sxs-lookup"><span data-stu-id="eb563-110">Array</span></span>



## <a name="output--t"></a><span data-ttu-id="eb563-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="eb563-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eb563-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb563-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eb563-113">&</span><span class="sxs-lookup"><span data-stu-id="eb563-113">'T</span></span>

<span data-ttu-id="eb563-114">の各要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="eb563-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="eb563-115">例</span><span class="sxs-lookup"><span data-stu-id="eb563-115">Example</span></span>

<span data-ttu-id="eb563-116">有名な整数シーケンスの奇数のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="eb563-116">Get the odd indexes in famous integer sequences.</span></span> <span data-ttu-id="eb563-117">(0 のインデックスは、シーケンスの _最初_ の値に対応していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="eb563-117">(note that the 0 index corresponds to the _first_ value of the sequence.)</span></span>

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famousOdd = Mapped(ElementsAt<Int>(0..2..9, _), [lucas, prime, fibonacci, catalan]);
// same as: famousOdd = [[2, 3, 7, 18, 47], [2, 5, 11, 17, 23], [0, 1, 3, 8, 21], [1, 2, 14, 132, 1430]]
```

## <a name="see-also"></a><span data-ttu-id="eb563-118">参照</span><span class="sxs-lookup"><span data-stu-id="eb563-118">See Also</span></span>

- [<span data-ttu-id="eb563-119">Microsoft...... ElementAt elementat</span><span class="sxs-lookup"><span data-stu-id="eb563-119">Microsoft.Quantum.Arrays.ElementAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementAt)
- [<span data-ttu-id="eb563-120">Microsoft. Quantum. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="eb563-120">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)