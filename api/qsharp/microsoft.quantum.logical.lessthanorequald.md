---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 7b0e9da379bd67eb78a80e7a535a15dcb8ba85c7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709947"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="6c88d-102">LessThanOrEqualD 関数</span><span class="sxs-lookup"><span data-stu-id="6c88d-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="6c88d-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6c88d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6c88d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6c88d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6c88d-105">数値が別の数値以下の場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="6c88d-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="6c88d-106">入力</span><span class="sxs-lookup"><span data-stu-id="6c88d-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="6c88d-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6c88d-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6c88d-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="6c88d-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="6c88d-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6c88d-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6c88d-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="6c88d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6c88d-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6c88d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6c88d-112">`true` が以下の場合 `a` にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="6c88d-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c88d-113">解説</span><span class="sxs-lookup"><span data-stu-id="6c88d-113">Remarks</span></span>

<span data-ttu-id="6c88d-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="6c88d-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```