---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 676defa7824e53578504c559c6d8f24b2ffc1a88
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711384"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="7fe29-102">GreaterThanL 関数</span><span class="sxs-lookup"><span data-stu-id="7fe29-102">GreaterThanL function</span></span>

<span data-ttu-id="7fe29-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7fe29-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7fe29-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7fe29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7fe29-105">数値が別の数値より大きい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="7fe29-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="7fe29-106">入力</span><span class="sxs-lookup"><span data-stu-id="7fe29-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="7fe29-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7fe29-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7fe29-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="7fe29-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="7fe29-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7fe29-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7fe29-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="7fe29-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7fe29-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7fe29-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7fe29-112">`true``a`が厳密により大きい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="7fe29-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7fe29-113">解説</span><span class="sxs-lookup"><span data-stu-id="7fe29-113">Remarks</span></span>

<span data-ttu-id="7fe29-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="7fe29-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```