---
uid: Microsoft.Quantum.Logical.EqualL
title: すべての関数を返します。
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f0a2bfa866068746e9c6e249573eb61c0d08c0f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710040"
---
# <a name="equall-function"></a><span data-ttu-id="a328a-102">すべての関数を返します。</span><span class="sxs-lookup"><span data-stu-id="a328a-102">EqualL function</span></span>

<span data-ttu-id="a328a-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a328a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a328a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a328a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a328a-105">2つの入力が等しい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="a328a-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="a328a-106">入力</span><span class="sxs-lookup"><span data-stu-id="a328a-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="a328a-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a328a-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a328a-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="a328a-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="a328a-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a328a-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a328a-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="a328a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a328a-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a328a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a328a-112">`true``a`がに等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="a328a-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a328a-113">解説</span><span class="sxs-lookup"><span data-stu-id="a328a-113">Remarks</span></span>

<span data-ttu-id="a328a-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a328a-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```