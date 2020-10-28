---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: d9e4cc5b0cfba3989ae64e494d0daa52069718a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720727"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="b6ffe-102">NotNearlyEqualD 関数</span><span class="sxs-lookup"><span data-stu-id="b6ffe-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="b6ffe-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b6ffe-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b6ffe-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6ffe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6ffe-105">2つの入力がほぼ等しくない場合 (つまり、許容範囲が 1e-12 の範囲内にない場合) にのみ、true を返します。</span><span class="sxs-lookup"><span data-stu-id="b6ffe-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b6ffe-106">入力</span><span class="sxs-lookup"><span data-stu-id="b6ffe-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="b6ffe-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6ffe-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6ffe-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="b6ffe-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="b6ffe-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6ffe-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6ffe-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="b6ffe-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b6ffe-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b6ffe-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b6ffe-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="b6ffe-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6ffe-113">解説</span><span class="sxs-lookup"><span data-stu-id="b6ffe-113">Remarks</span></span>

<span data-ttu-id="b6ffe-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b6ffe-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```