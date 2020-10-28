---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713232"
---
# <a name="rangereverse-function"></a><span data-ttu-id="8b36b-102">RangeReverse 関数</span><span class="sxs-lookup"><span data-stu-id="8b36b-102">RangeReverse function</span></span>

<span data-ttu-id="8b36b-103">名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="8b36b-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="8b36b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b36b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b36b-105">入力範囲の逆の新しい範囲を返します。</span><span class="sxs-lookup"><span data-stu-id="8b36b-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="8b36b-106">入力</span><span class="sxs-lookup"><span data-stu-id="8b36b-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="8b36b-107">r: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="8b36b-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="8b36b-108">入力範囲。</span><span class="sxs-lookup"><span data-stu-id="8b36b-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="8b36b-109">出力: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="8b36b-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="8b36b-110">指定された範囲の逆の新しい範囲。</span><span class="sxs-lookup"><span data-stu-id="8b36b-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b36b-111">解説</span><span class="sxs-lookup"><span data-stu-id="8b36b-111">Remarks</span></span>

<span data-ttu-id="8b36b-112">範囲の最後の要素はと同じでない可能性があるため、範囲の反転は単に.. `end` `-step` .. `start` ではないことに注意 `end` してください。</span><span class="sxs-lookup"><span data-stu-id="8b36b-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>