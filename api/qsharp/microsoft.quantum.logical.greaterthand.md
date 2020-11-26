---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: c23d85cf513bb6d37e67260eeeb3b81b42e6771a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198029"
---
# <a name="greaterthand-function"></a><span data-ttu-id="c08ef-102">GreaterThanD 関数</span><span class="sxs-lookup"><span data-stu-id="c08ef-102">GreaterThanD function</span></span>

<span data-ttu-id="c08ef-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c08ef-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c08ef-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c08ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c08ef-105">数値が別の数値より大きい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="c08ef-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c08ef-106">入力</span><span class="sxs-lookup"><span data-stu-id="c08ef-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="c08ef-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c08ef-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c08ef-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="c08ef-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="c08ef-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c08ef-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c08ef-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="c08ef-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c08ef-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c08ef-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c08ef-112">`true``a`が厳密により大きい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="c08ef-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c08ef-113">解説</span><span class="sxs-lookup"><span data-stu-id="c08ef-113">Remarks</span></span>

<span data-ttu-id="c08ef-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c08ef-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```