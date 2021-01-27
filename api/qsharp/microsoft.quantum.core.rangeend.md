---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 196fab0bd97a441a16976033dc0d660c54cdfd6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831366"
---
# <a name="rangeend-function"></a><span data-ttu-id="64a48-102">RangeEnd 関数</span><span class="sxs-lookup"><span data-stu-id="64a48-102">RangeEnd function</span></span>

<span data-ttu-id="64a48-103">名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="64a48-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="64a48-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="64a48-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="64a48-105">指定された範囲の定義済みの終了値を返します。これは必ずしもシーケンスの最後の要素ではありません。</span><span class="sxs-lookup"><span data-stu-id="64a48-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="64a48-106">入力</span><span class="sxs-lookup"><span data-stu-id="64a48-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="64a48-107">範囲: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="64a48-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="64a48-108">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="64a48-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="64a48-109">指定された範囲の定義済みの終了値。</span><span class="sxs-lookup"><span data-stu-id="64a48-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="64a48-110">解説</span><span class="sxs-lookup"><span data-stu-id="64a48-110">Remarks</span></span>

<span data-ttu-id="64a48-111">範囲式の最初の要素は `start` で、2番目の要素は、3番目の要素はなど `start+step` `start+step+step` です。が渡されるまで、が `end` 渡されます。</span><span class="sxs-lookup"><span data-stu-id="64a48-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="64a48-112">範囲の定義済みの終了値は、範囲によって指定されたシーケンスの最後の要素と異なる場合があることに注意してください。たとえば、0 ~ の範囲で指定します。</span><span class="sxs-lookup"><span data-stu-id="64a48-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="64a48-113">2..</span><span class="sxs-lookup"><span data-stu-id="64a48-113">2 ..</span></span> <span data-ttu-id="64a48-114">5最後の要素は4ですが、終了値は5です。</span><span class="sxs-lookup"><span data-stu-id="64a48-114">5 the last element is 4 but the end value is 5.</span></span>