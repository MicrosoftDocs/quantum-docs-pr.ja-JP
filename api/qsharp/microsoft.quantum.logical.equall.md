---
uid: Microsoft.Quantum.Logical.EqualL
title: すべての関数を返します。
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 58086f40ea20b6f1a5fa6996e3a6703e2bf66306
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815988"
---
# <a name="equall-function"></a><span data-ttu-id="387b6-102">すべての関数を返します。</span><span class="sxs-lookup"><span data-stu-id="387b6-102">EqualL function</span></span>

<span data-ttu-id="387b6-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="387b6-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="387b6-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="387b6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="387b6-105">2つの入力が等しい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="387b6-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="387b6-106">入力</span><span class="sxs-lookup"><span data-stu-id="387b6-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="387b6-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="387b6-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="387b6-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="387b6-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="387b6-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="387b6-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="387b6-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="387b6-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="387b6-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="387b6-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="387b6-112">`true``a`がに等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="387b6-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="387b6-113">解説</span><span class="sxs-lookup"><span data-stu-id="387b6-113">Remarks</span></span>

<span data-ttu-id="387b6-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="387b6-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualL(a, b);
```