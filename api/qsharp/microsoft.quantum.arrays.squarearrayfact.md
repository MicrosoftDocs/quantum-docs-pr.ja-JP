---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: f7f0573db9098feebfd481624e11119c58fd9eed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718855"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="c4212-102">SquareArrayFact 関数</span><span class="sxs-lookup"><span data-stu-id="c4212-102">SquareArrayFact function</span></span>

<span data-ttu-id="c4212-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c4212-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c4212-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4212-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4212-105">2次元配列に正方形の形状がある条件を表します。</span><span class="sxs-lookup"><span data-stu-id="c4212-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="c4212-106">説明</span><span class="sxs-lookup"><span data-stu-id="c4212-106">Description</span></span>

<span data-ttu-id="c4212-107">この関数は、配列内の各行に、配列内の行 (要素) と同じ数の要素があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="c4212-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="c4212-108">入力</span><span class="sxs-lookup"><span data-stu-id="c4212-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="c4212-109">配列: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="c4212-109">array : 'T[][]</span></span>

<span data-ttu-id="c4212-110">2次元の要素の配列。</span><span class="sxs-lookup"><span data-stu-id="c4212-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="c4212-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c4212-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c4212-112">配列が正方形配列でない場合に出力されるメッセージ</span><span class="sxs-lookup"><span data-stu-id="c4212-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="c4212-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4212-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c4212-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="c4212-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4212-115">&</span><span class="sxs-lookup"><span data-stu-id="c4212-115">'T</span></span>

<span data-ttu-id="c4212-116">の各要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="c4212-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4212-117">参照</span><span class="sxs-lookup"><span data-stu-id="c4212-117">See Also</span></span>

- [<span data-ttu-id="c4212-118">RectangularArrayFact です。</span><span class="sxs-lookup"><span data-stu-id="c4212-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)