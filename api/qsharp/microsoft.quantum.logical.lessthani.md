---
uid: Microsoft.Quantum.Logical.LessThanI
title: 機能していない関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 5d5b17c8481ccf58b8e4fc4bb958e0adbf6d8f00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197774"
---
# <a name="lessthani-function"></a><span data-ttu-id="abd3b-102">機能していない関数</span><span class="sxs-lookup"><span data-stu-id="abd3b-102">LessThanI function</span></span>

<span data-ttu-id="abd3b-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="abd3b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="abd3b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="abd3b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="abd3b-105">数値が別の数値より小さい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="abd3b-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="abd3b-106">入力</span><span class="sxs-lookup"><span data-stu-id="abd3b-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="abd3b-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="abd3b-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="abd3b-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="abd3b-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="abd3b-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="abd3b-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="abd3b-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="abd3b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="abd3b-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="abd3b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="abd3b-112">`true``a`が厳密により小さい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="abd3b-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="abd3b-113">解説</span><span class="sxs-lookup"><span data-stu-id="abd3b-113">Remarks</span></span>

<span data-ttu-id="abd3b-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="abd3b-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```