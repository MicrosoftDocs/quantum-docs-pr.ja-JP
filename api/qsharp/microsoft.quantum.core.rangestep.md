---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 39c8581fe795a1b76d2a6e81c238a271287c2c38
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213805"
---
# <a name="rangestep-function"></a><span data-ttu-id="e09f1-102">RangeStep 関数</span><span class="sxs-lookup"><span data-stu-id="e09f1-102">RangeStep function</span></span>

<span data-ttu-id="e09f1-103">名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="e09f1-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="e09f1-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="e09f1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e09f1-105">範囲の次の値を計算する方法を指定する整数を返します。</span><span class="sxs-lookup"><span data-stu-id="e09f1-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="e09f1-106">入力</span><span class="sxs-lookup"><span data-stu-id="e09f1-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="e09f1-107">範囲: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="e09f1-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="e09f1-108">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e09f1-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e09f1-109">指定された範囲の定義されたステップ値。</span><span class="sxs-lookup"><span data-stu-id="e09f1-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="e09f1-110">解説</span><span class="sxs-lookup"><span data-stu-id="e09f1-110">Remarks</span></span>

<span data-ttu-id="e09f1-111">範囲式の最初の要素は `start` で、2番目の要素は、3番目の要素はなど `start+step` `start+step+step` です。が渡されるまで、が `end` 渡されます。</span><span class="sxs-lookup"><span data-stu-id="e09f1-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>