---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 246fad15c691a53fcc5be10f2c713672e0b54e6b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197468"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="7e13e-102">NearlyEqualD 関数</span><span class="sxs-lookup"><span data-stu-id="7e13e-102">NearlyEqualD function</span></span>

<span data-ttu-id="7e13e-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7e13e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7e13e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e13e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7e13e-105">2つの入力がほぼ等しい場合 (つまり、許容範囲が 1e-12 の範囲内) の場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="7e13e-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="7e13e-106">入力</span><span class="sxs-lookup"><span data-stu-id="7e13e-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="7e13e-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7e13e-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7e13e-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="7e13e-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="7e13e-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7e13e-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7e13e-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="7e13e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7e13e-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7e13e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7e13e-112">`true``a`がとほぼ等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="7e13e-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e13e-113">解説</span><span class="sxs-lookup"><span data-stu-id="7e13e-113">Remarks</span></span>

<span data-ttu-id="7e13e-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="7e13e-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```