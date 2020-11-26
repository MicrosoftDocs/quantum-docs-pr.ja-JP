---
uid: Microsoft.Quantum.Logical.LessThanL
title: ない関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 9a0678569596ac188c87c3944f3759783fcc77ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197723"
---
# <a name="lessthanl-function"></a><span data-ttu-id="53201-102">ない関数</span><span class="sxs-lookup"><span data-stu-id="53201-102">LessThanL function</span></span>

<span data-ttu-id="53201-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="53201-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="53201-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="53201-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="53201-105">数値が別の数値より小さい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="53201-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="53201-106">入力</span><span class="sxs-lookup"><span data-stu-id="53201-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="53201-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="53201-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="53201-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="53201-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="53201-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="53201-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="53201-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="53201-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="53201-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="53201-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="53201-112">`true``a`が厳密により小さい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="53201-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="53201-113">解説</span><span class="sxs-lookup"><span data-stu-id="53201-113">Remarks</span></span>

<span data-ttu-id="53201-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="53201-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```