---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 2247c1c1ae8b37b59e87c0c68b06fd1094c9003b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849199"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="5cf28-102">GreaterThanL 関数</span><span class="sxs-lookup"><span data-stu-id="5cf28-102">GreaterThanL function</span></span>

<span data-ttu-id="5cf28-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5cf28-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5cf28-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5cf28-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5cf28-105">数値が別の数値より大きい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="5cf28-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="5cf28-106">入力</span><span class="sxs-lookup"><span data-stu-id="5cf28-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="5cf28-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5cf28-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5cf28-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="5cf28-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="5cf28-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5cf28-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5cf28-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="5cf28-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5cf28-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5cf28-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5cf28-112">`true``a`が厳密により大きい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="5cf28-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5cf28-113">解説</span><span class="sxs-lookup"><span data-stu-id="5cf28-113">Remarks</span></span>

<span data-ttu-id="5cf28-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5cf28-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanL(a, b);
```