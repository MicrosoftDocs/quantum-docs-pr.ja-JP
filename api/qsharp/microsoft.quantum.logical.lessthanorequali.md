---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: b2974c9bc84d0b4366767f47682ab542f85063e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197568"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="79db9-102">LessThanOrEqualI 関数</span><span class="sxs-lookup"><span data-stu-id="79db9-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="79db9-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="79db9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="79db9-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79db9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="79db9-105">数値が別の数値以下の場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="79db9-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="79db9-106">入力</span><span class="sxs-lookup"><span data-stu-id="79db9-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="79db9-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="79db9-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="79db9-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="79db9-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="79db9-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="79db9-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="79db9-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="79db9-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="79db9-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="79db9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="79db9-112">`true` が以下の場合 `a` にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="79db9-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="79db9-113">解説</span><span class="sxs-lookup"><span data-stu-id="79db9-113">Remarks</span></span>

<span data-ttu-id="79db9-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="79db9-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```