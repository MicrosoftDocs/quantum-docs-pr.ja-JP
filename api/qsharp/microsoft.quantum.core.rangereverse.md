---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213839"
---
# <a name="rangereverse-function"></a><span data-ttu-id="385c6-102">RangeReverse 関数</span><span class="sxs-lookup"><span data-stu-id="385c6-102">RangeReverse function</span></span>

<span data-ttu-id="385c6-103">名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="385c6-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="385c6-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="385c6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="385c6-105">入力範囲の逆の新しい範囲を返します。</span><span class="sxs-lookup"><span data-stu-id="385c6-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="385c6-106">入力</span><span class="sxs-lookup"><span data-stu-id="385c6-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="385c6-107">r: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="385c6-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="385c6-108">入力範囲。</span><span class="sxs-lookup"><span data-stu-id="385c6-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="385c6-109">出力: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="385c6-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="385c6-110">指定された範囲の逆の新しい範囲。</span><span class="sxs-lookup"><span data-stu-id="385c6-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="385c6-111">解説</span><span class="sxs-lookup"><span data-stu-id="385c6-111">Remarks</span></span>

<span data-ttu-id="385c6-112">範囲の最後の要素はと同じでない可能性があるため、範囲の反転は単に.. `end` `-step` .. `start` ではないことに注意 `end` してください。</span><span class="sxs-lookup"><span data-stu-id="385c6-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>