---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 20414e80e08993a18331a8f0b385a1e4cc1255b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710003"
---
# <a name="greaterthand-function"></a><span data-ttu-id="10d99-102">GreaterThanD 関数</span><span class="sxs-lookup"><span data-stu-id="10d99-102">GreaterThanD function</span></span>

<span data-ttu-id="10d99-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="10d99-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="10d99-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="10d99-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="10d99-105">数値が別の数値より大きい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="10d99-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="10d99-106">入力</span><span class="sxs-lookup"><span data-stu-id="10d99-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="10d99-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="10d99-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="10d99-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="10d99-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="10d99-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="10d99-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="10d99-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="10d99-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="10d99-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="10d99-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="10d99-112">`true``a`が厳密により大きい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="10d99-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="10d99-113">解説</span><span class="sxs-lookup"><span data-stu-id="10d99-113">Remarks</span></span>

<span data-ttu-id="10d99-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="10d99-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```