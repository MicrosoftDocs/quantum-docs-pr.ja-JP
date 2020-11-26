---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220945"
---
# <a name="indexrange-function"></a><span data-ttu-id="64ef4-102">IndexRange 関数</span><span class="sxs-lookup"><span data-stu-id="64ef4-102">IndexRange function</span></span>

<span data-ttu-id="64ef4-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="64ef4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="64ef4-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="64ef4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="64ef4-105">配列を指定した場合は、その配列のインデックスに対する範囲を返します。 for ループでの使用に適しています。</span><span class="sxs-lookup"><span data-stu-id="64ef4-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="64ef4-106">入力</span><span class="sxs-lookup"><span data-stu-id="64ef4-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="64ef4-107">配列: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="64ef4-107">array : 'TElement[]</span></span>

<span data-ttu-id="64ef4-108">インデックスの範囲を返す対象の配列。</span><span class="sxs-lookup"><span data-stu-id="64ef4-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="64ef4-109">出力: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="64ef4-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="64ef4-110">配列のすべてのインデックスの範囲。</span><span class="sxs-lookup"><span data-stu-id="64ef4-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="64ef4-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="64ef4-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="64ef4-112">' TElement '</span><span class="sxs-lookup"><span data-stu-id="64ef4-112">'TElement</span></span>

<span data-ttu-id="64ef4-113">配列の要素の型。</span><span class="sxs-lookup"><span data-stu-id="64ef4-113">The type of elements of the array.</span></span>