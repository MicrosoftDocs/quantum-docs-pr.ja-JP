---
uid: Microsoft.Quantum.Logical.LessThanL
title: ない関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: fde57bcd9960056461bddac54300c298def8f7d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709956"
---
# <a name="lessthanl-function"></a><span data-ttu-id="b86de-102">ない関数</span><span class="sxs-lookup"><span data-stu-id="b86de-102">LessThanL function</span></span>

<span data-ttu-id="b86de-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b86de-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b86de-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b86de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b86de-105">数値が別の数値より小さい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="b86de-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="b86de-106">入力</span><span class="sxs-lookup"><span data-stu-id="b86de-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="b86de-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b86de-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b86de-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="b86de-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="b86de-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b86de-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b86de-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="b86de-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b86de-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b86de-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b86de-112">`true``a`が厳密により小さい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="b86de-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b86de-113">解説</span><span class="sxs-lookup"><span data-stu-id="b86de-113">Remarks</span></span>

<span data-ttu-id="b86de-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b86de-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```