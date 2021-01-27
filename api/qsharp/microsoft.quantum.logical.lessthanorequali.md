---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 9438fc05b4ccb041b087f9cfeb30ac0c8cfcabd6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815608"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="40fe0-102">LessThanOrEqualI 関数</span><span class="sxs-lookup"><span data-stu-id="40fe0-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="40fe0-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="40fe0-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="40fe0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="40fe0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="40fe0-105">数値が別の数値以下の場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="40fe0-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="40fe0-106">入力</span><span class="sxs-lookup"><span data-stu-id="40fe0-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="40fe0-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="40fe0-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="40fe0-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="40fe0-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="40fe0-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="40fe0-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="40fe0-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="40fe0-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="40fe0-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="40fe0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="40fe0-112">`true` が以下の場合 `a` にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="40fe0-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="40fe0-113">解説</span><span class="sxs-lookup"><span data-stu-id="40fe0-113">Remarks</span></span>

<span data-ttu-id="40fe0-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="40fe0-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```