---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0c9fa353b549d3c137beac3bcc3cfb0e742f6d07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197808"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="b6004-102">GreaterThanOrEqualD 関数</span><span class="sxs-lookup"><span data-stu-id="b6004-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="b6004-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b6004-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b6004-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6004-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6004-105">数値がもう1つの数値以上の場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="b6004-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b6004-106">入力</span><span class="sxs-lookup"><span data-stu-id="b6004-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="b6004-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6004-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6004-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="b6004-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="b6004-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6004-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6004-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="b6004-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b6004-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b6004-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b6004-112">`true``a`がより大きいか、またはと等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="b6004-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6004-113">解説</span><span class="sxs-lookup"><span data-stu-id="b6004-113">Remarks</span></span>

<span data-ttu-id="b6004-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b6004-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```