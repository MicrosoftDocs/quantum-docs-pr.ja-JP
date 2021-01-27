---
uid: Microsoft.Quantum.Logical.LessThanL
title: ない関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: d5753f9e1447fc1bd433703037fe44c86aaa659c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849148"
---
# <a name="lessthanl-function"></a><span data-ttu-id="2a284-102">ない関数</span><span class="sxs-lookup"><span data-stu-id="2a284-102">LessThanL function</span></span>

<span data-ttu-id="2a284-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2a284-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2a284-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2a284-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2a284-105">数値が別の数値より小さい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="2a284-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="2a284-106">入力</span><span class="sxs-lookup"><span data-stu-id="2a284-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="2a284-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2a284-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2a284-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="2a284-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="2a284-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2a284-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2a284-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="2a284-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2a284-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2a284-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2a284-112">`true``a`が厳密により小さい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="2a284-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a284-113">解説</span><span class="sxs-lookup"><span data-stu-id="2a284-113">Remarks</span></span>

<span data-ttu-id="2a284-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2a284-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanL(a, b);
```