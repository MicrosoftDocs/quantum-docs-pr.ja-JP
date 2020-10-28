---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718922"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="295c0-102">RectangularArrayFact 関数</span><span class="sxs-lookup"><span data-stu-id="295c0-102">RectangularArrayFact function</span></span>

<span data-ttu-id="295c0-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="295c0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="295c0-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="295c0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="295c0-105">2次元配列に四角形の形状がある条件を表します。</span><span class="sxs-lookup"><span data-stu-id="295c0-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="295c0-106">説明</span><span class="sxs-lookup"><span data-stu-id="295c0-106">Description</span></span>

<span data-ttu-id="295c0-107">この関数は、配列内の各行の長さが同じであることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="295c0-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="295c0-108">入力</span><span class="sxs-lookup"><span data-stu-id="295c0-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="295c0-109">配列: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="295c0-109">array : 'T[][]</span></span>

<span data-ttu-id="295c0-110">2次元の要素の配列。</span><span class="sxs-lookup"><span data-stu-id="295c0-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="295c0-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="295c0-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="295c0-112">配列が四角形の配列でない場合に印刷されるメッセージ</span><span class="sxs-lookup"><span data-stu-id="295c0-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="295c0-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="295c0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="295c0-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="295c0-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="295c0-115">&</span><span class="sxs-lookup"><span data-stu-id="295c0-115">'T</span></span>

<span data-ttu-id="295c0-116">の各要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="295c0-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="295c0-117">参照</span><span class="sxs-lookup"><span data-stu-id="295c0-117">See Also</span></span>

- [<span data-ttu-id="295c0-118">SquareArrayFact です。</span><span class="sxs-lookup"><span data-stu-id="295c0-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)