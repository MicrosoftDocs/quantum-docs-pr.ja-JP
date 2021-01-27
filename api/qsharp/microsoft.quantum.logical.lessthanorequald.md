---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 703b782efe9daccd4f6a339481d49ae9232123f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849137"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="cc84f-102">LessThanOrEqualD 関数</span><span class="sxs-lookup"><span data-stu-id="cc84f-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="cc84f-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cc84f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cc84f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc84f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc84f-105">数値が別の数値以下の場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="cc84f-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="cc84f-106">入力</span><span class="sxs-lookup"><span data-stu-id="cc84f-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="cc84f-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cc84f-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cc84f-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="cc84f-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="cc84f-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cc84f-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cc84f-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="cc84f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cc84f-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cc84f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cc84f-112">`true` が以下の場合 `a` にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="cc84f-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc84f-113">解説</span><span class="sxs-lookup"><span data-stu-id="cc84f-113">Remarks</span></span>

<span data-ttu-id="cc84f-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="cc84f-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```