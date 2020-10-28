---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: ffd00d8086654a2d783a351fe254fb2ee35b9184
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709984"
---
# <a name="greaterthani-function"></a><span data-ttu-id="b1056-102">GreaterThanI 関数</span><span class="sxs-lookup"><span data-stu-id="b1056-102">GreaterThanI function</span></span>

<span data-ttu-id="b1056-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b1056-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b1056-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b1056-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b1056-105">数値が別の数値より大きい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="b1056-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="b1056-106">入力</span><span class="sxs-lookup"><span data-stu-id="b1056-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="b1056-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b1056-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b1056-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="b1056-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="b1056-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b1056-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b1056-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="b1056-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b1056-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b1056-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b1056-112">`true``a`が厳密により大きい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="b1056-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1056-113">解説</span><span class="sxs-lookup"><span data-stu-id="b1056-113">Remarks</span></span>

<span data-ttu-id="b1056-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b1056-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```