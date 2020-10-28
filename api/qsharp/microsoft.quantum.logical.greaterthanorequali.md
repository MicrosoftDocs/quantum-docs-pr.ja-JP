---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 292599c18d2aac44cef8f0eecca38eb1fbe22061
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723498"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="642e3-102">GreaterThanOrEqualI 関数</span><span class="sxs-lookup"><span data-stu-id="642e3-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="642e3-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="642e3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="642e3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="642e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="642e3-105">数値がもう1つの数値以上の場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="642e3-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="642e3-106">入力</span><span class="sxs-lookup"><span data-stu-id="642e3-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="642e3-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="642e3-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="642e3-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="642e3-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="642e3-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="642e3-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="642e3-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="642e3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="642e3-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="642e3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="642e3-112">`true``a`がより大きいか、またはと等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="642e3-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="642e3-113">解説</span><span class="sxs-lookup"><span data-stu-id="642e3-113">Remarks</span></span>

<span data-ttu-id="642e3-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="642e3-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```