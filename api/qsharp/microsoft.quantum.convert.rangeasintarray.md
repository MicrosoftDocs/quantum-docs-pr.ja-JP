---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214009"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="3b4d2-102">RangeAsIntArray 関数</span><span class="sxs-lookup"><span data-stu-id="3b4d2-102">RangeAsIntArray function</span></span>

<span data-ttu-id="3b4d2-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="3b4d2-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="3b4d2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3b4d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3b4d2-105">Start. で列挙された整数の配列を作成します `arr` 。ステップ..終わり。</span><span class="sxs-lookup"><span data-stu-id="3b4d2-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="3b4d2-106">入力</span><span class="sxs-lookup"><span data-stu-id="3b4d2-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="3b4d2-107">範囲: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="3b4d2-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="3b4d2-108">`Range` `start..step..end` 配列に変換する値の。</span><span class="sxs-lookup"><span data-stu-id="3b4d2-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="3b4d2-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3b4d2-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3b4d2-110">によって反復処理される値に対応する整数の新しい配列 `range` 。</span><span class="sxs-lookup"><span data-stu-id="3b4d2-110">A new array of integers corresponding to values iterated over by `range`.</span></span>