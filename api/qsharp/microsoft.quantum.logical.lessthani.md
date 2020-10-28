---
uid: Microsoft.Quantum.Logical.LessThanI
title: 機能していない関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 204e62a87d2b3d0070946985030d038ead686457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723484"
---
# <a name="lessthani-function"></a><span data-ttu-id="9247b-102">機能していない関数</span><span class="sxs-lookup"><span data-stu-id="9247b-102">LessThanI function</span></span>

<span data-ttu-id="9247b-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="9247b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="9247b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9247b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9247b-105">数値が別の数値より小さい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="9247b-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="9247b-106">入力</span><span class="sxs-lookup"><span data-stu-id="9247b-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="9247b-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9247b-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9247b-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="9247b-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="9247b-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9247b-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9247b-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="9247b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9247b-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9247b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9247b-112">`true``a`が厳密により小さい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="9247b-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9247b-113">解説</span><span class="sxs-lookup"><span data-stu-id="9247b-113">Remarks</span></span>

<span data-ttu-id="9247b-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9247b-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```