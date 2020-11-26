---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 44683b204ecd469f5f5412a7ec06e98ec8a4f37e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224005"
---
# <a name="rangestart-function"></a><span data-ttu-id="1aba1-102">RangeStart 関数</span><span class="sxs-lookup"><span data-stu-id="1aba1-102">RangeStart function</span></span>

<span data-ttu-id="1aba1-103">名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="1aba1-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="1aba1-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="1aba1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1aba1-105">指定された範囲の開始値を定義して返します。</span><span class="sxs-lookup"><span data-stu-id="1aba1-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="1aba1-106">入力</span><span class="sxs-lookup"><span data-stu-id="1aba1-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="1aba1-107">範囲: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="1aba1-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="1aba1-108">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1aba1-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1aba1-109">指定された範囲の開始値。</span><span class="sxs-lookup"><span data-stu-id="1aba1-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="1aba1-110">解説</span><span class="sxs-lookup"><span data-stu-id="1aba1-110">Remarks</span></span>

<span data-ttu-id="1aba1-111">範囲式の最初の要素は `start` で、2番目の要素は、3番目の要素はなど `start+step` `start+step+step` です。が渡されるまで、が `end` 渡されます。</span><span class="sxs-lookup"><span data-stu-id="1aba1-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="1aba1-112">範囲で空のシーケンスが指定されていない限り、範囲の定義済みの開始値が、シーケンスの最初の要素と同じであることに注意してください (例: 2..</span><span class="sxs-lookup"><span data-stu-id="1aba1-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="1aba1-113">1)。</span><span class="sxs-lookup"><span data-stu-id="1aba1-113">1).</span></span>