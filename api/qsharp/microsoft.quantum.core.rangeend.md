---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713246"
---
# <a name="rangeend-function"></a><span data-ttu-id="9c95d-102">RangeEnd 関数</span><span class="sxs-lookup"><span data-stu-id="9c95d-102">RangeEnd function</span></span>

<span data-ttu-id="9c95d-103">名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="9c95d-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="9c95d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c95d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c95d-105">指定された範囲の定義済みの終了値を返します。これは必ずしもシーケンスの最後の要素ではありません。</span><span class="sxs-lookup"><span data-stu-id="9c95d-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="9c95d-106">入力</span><span class="sxs-lookup"><span data-stu-id="9c95d-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="9c95d-107">範囲: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="9c95d-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="9c95d-108">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c95d-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9c95d-109">指定された範囲の定義済みの終了値。</span><span class="sxs-lookup"><span data-stu-id="9c95d-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c95d-110">解説</span><span class="sxs-lookup"><span data-stu-id="9c95d-110">Remarks</span></span>

<span data-ttu-id="9c95d-111">範囲式の最初の要素は `start` で、2番目の要素は、3番目の要素はなど `start+step` `start+step+step` です。が渡されるまで、が `end` 渡されます。</span><span class="sxs-lookup"><span data-stu-id="9c95d-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="9c95d-112">範囲の定義済みの終了値は、範囲によって指定されたシーケンスの最後の要素と異なる場合があることに注意してください。たとえば、0 ~ の範囲で指定します。</span><span class="sxs-lookup"><span data-stu-id="9c95d-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="9c95d-113">2..</span><span class="sxs-lookup"><span data-stu-id="9c95d-113">2 ..</span></span> <span data-ttu-id="9c95d-114">5最後の要素は4ですが、終了値は5です。</span><span class="sxs-lookup"><span data-stu-id="9c95d-114">5 the last element is 4 but the end value is 5.</span></span>