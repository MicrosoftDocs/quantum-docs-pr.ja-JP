---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: a59a9eca2941a44a70ec5a379b146ac459390bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722644"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="4e7dd-102">GreaterThanOrEqualL 関数</span><span class="sxs-lookup"><span data-stu-id="4e7dd-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="4e7dd-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4e7dd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4e7dd-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e7dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e7dd-105">数値がもう1つの数値以上の場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="4e7dd-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="4e7dd-106">入力</span><span class="sxs-lookup"><span data-stu-id="4e7dd-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4e7dd-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4e7dd-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4e7dd-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="4e7dd-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4e7dd-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4e7dd-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4e7dd-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="4e7dd-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4e7dd-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4e7dd-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4e7dd-112">`true``a`がより大きいか、またはと等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="4e7dd-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e7dd-113">解説</span><span class="sxs-lookup"><span data-stu-id="4e7dd-113">Remarks</span></span>

<span data-ttu-id="4e7dd-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="4e7dd-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```