---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: 3529718f0c903266d21fd593c11c0149dae0fa2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220197"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="03dd2-102">SquareArrayFact 関数</span><span class="sxs-lookup"><span data-stu-id="03dd2-102">SquareArrayFact function</span></span>

<span data-ttu-id="03dd2-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="03dd2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="03dd2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03dd2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03dd2-105">2次元配列に正方形の形状がある条件を表します。</span><span class="sxs-lookup"><span data-stu-id="03dd2-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="03dd2-106">説明</span><span class="sxs-lookup"><span data-stu-id="03dd2-106">Description</span></span>

<span data-ttu-id="03dd2-107">この関数は、配列内の各行に、配列内の行 (要素) と同じ数の要素があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="03dd2-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="03dd2-108">入力</span><span class="sxs-lookup"><span data-stu-id="03dd2-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="03dd2-109">配列: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="03dd2-109">array : 'T[][]</span></span>

<span data-ttu-id="03dd2-110">2次元の要素の配列。</span><span class="sxs-lookup"><span data-stu-id="03dd2-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="03dd2-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="03dd2-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="03dd2-112">配列が正方形配列でない場合に出力されるメッセージ</span><span class="sxs-lookup"><span data-stu-id="03dd2-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="03dd2-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="03dd2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="03dd2-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="03dd2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="03dd2-115">&</span><span class="sxs-lookup"><span data-stu-id="03dd2-115">'T</span></span>

<span data-ttu-id="03dd2-116">の各要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="03dd2-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="03dd2-117">参照</span><span class="sxs-lookup"><span data-stu-id="03dd2-117">See Also</span></span>

- [<span data-ttu-id="03dd2-118">RectangularArrayFact です。</span><span class="sxs-lookup"><span data-stu-id="03dd2-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)