---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 8cd274d5e299df2f556006baf7457d54aebcd071
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723489"
---
# <a name="lessthand-function"></a><span data-ttu-id="93ae5-102">LessThanD 関数</span><span class="sxs-lookup"><span data-stu-id="93ae5-102">LessThanD function</span></span>

<span data-ttu-id="93ae5-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="93ae5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="93ae5-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93ae5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93ae5-105">数値が別の数値より小さい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="93ae5-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="93ae5-106">入力</span><span class="sxs-lookup"><span data-stu-id="93ae5-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="93ae5-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="93ae5-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="93ae5-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="93ae5-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="93ae5-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="93ae5-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="93ae5-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="93ae5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="93ae5-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="93ae5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="93ae5-112">`true``a`が厳密により小さい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="93ae5-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="93ae5-113">解説</span><span class="sxs-lookup"><span data-stu-id="93ae5-113">Remarks</span></span>

<span data-ttu-id="93ae5-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="93ae5-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```