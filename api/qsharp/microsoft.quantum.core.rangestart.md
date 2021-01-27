---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831116"
---
# <a name="rangestart-function"></a><span data-ttu-id="e1db8-102">RangeStart 関数</span><span class="sxs-lookup"><span data-stu-id="e1db8-102">RangeStart function</span></span>

<span data-ttu-id="e1db8-103">名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="e1db8-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="e1db8-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="e1db8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e1db8-105">指定された範囲の開始値を定義して返します。</span><span class="sxs-lookup"><span data-stu-id="e1db8-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="e1db8-106">入力</span><span class="sxs-lookup"><span data-stu-id="e1db8-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="e1db8-107">範囲: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="e1db8-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="e1db8-108">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1db8-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e1db8-109">指定された範囲の開始値。</span><span class="sxs-lookup"><span data-stu-id="e1db8-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1db8-110">解説</span><span class="sxs-lookup"><span data-stu-id="e1db8-110">Remarks</span></span>

<span data-ttu-id="e1db8-111">範囲式の最初の要素は `start` で、2番目の要素は、3番目の要素はなど `start+step` `start+step+step` です。が渡されるまで、が `end` 渡されます。</span><span class="sxs-lookup"><span data-stu-id="e1db8-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="e1db8-112">範囲で空のシーケンスが指定されていない限り、範囲の定義済みの開始値が、シーケンスの最初の要素と同じであることに注意してください (例: 2..</span><span class="sxs-lookup"><span data-stu-id="e1db8-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="e1db8-113">1)。</span><span class="sxs-lookup"><span data-stu-id="e1db8-113">1).</span></span>