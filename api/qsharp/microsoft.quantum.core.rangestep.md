---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713162"
---
# <a name="rangestep-function"></a><span data-ttu-id="df347-102">RangeStep 関数</span><span class="sxs-lookup"><span data-stu-id="df347-102">RangeStep function</span></span>

<span data-ttu-id="df347-103">名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="df347-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="df347-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df347-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df347-105">範囲の次の値を計算する方法を指定する整数を返します。</span><span class="sxs-lookup"><span data-stu-id="df347-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="df347-106">入力</span><span class="sxs-lookup"><span data-stu-id="df347-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="df347-107">範囲: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="df347-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="df347-108">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df347-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df347-109">指定された範囲の定義されたステップ値。</span><span class="sxs-lookup"><span data-stu-id="df347-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="df347-110">解説</span><span class="sxs-lookup"><span data-stu-id="df347-110">Remarks</span></span>

<span data-ttu-id="df347-111">範囲式の最初の要素は `start` で、2番目の要素は、3番目の要素はなど `start+step` `start+step+step` です。が渡されるまで、が `end` 渡されます。</span><span class="sxs-lookup"><span data-stu-id="df347-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>