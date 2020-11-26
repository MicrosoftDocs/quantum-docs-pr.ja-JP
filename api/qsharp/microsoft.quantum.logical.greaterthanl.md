---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 5e1b2adab36b7937c83ea912b8a9cb148b626ee5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197978"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="d9354-102">GreaterThanL 関数</span><span class="sxs-lookup"><span data-stu-id="d9354-102">GreaterThanL function</span></span>

<span data-ttu-id="d9354-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d9354-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d9354-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9354-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9354-105">数値が別の数値より大きい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="d9354-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="d9354-106">入力</span><span class="sxs-lookup"><span data-stu-id="d9354-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="d9354-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d9354-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d9354-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="d9354-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="d9354-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d9354-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d9354-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="d9354-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d9354-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d9354-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d9354-112">`true``a`が厳密により大きい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="d9354-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9354-113">解説</span><span class="sxs-lookup"><span data-stu-id="d9354-113">Remarks</span></span>

<span data-ttu-id="d9354-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d9354-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```