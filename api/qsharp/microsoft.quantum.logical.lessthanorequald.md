---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 3f4ccb0888e7df7c43ff73be8a3140e3fa84d4dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197638"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="01e01-102">LessThanOrEqualD 関数</span><span class="sxs-lookup"><span data-stu-id="01e01-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="01e01-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="01e01-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="01e01-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="01e01-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="01e01-105">数値が別の数値以下の場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="01e01-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="01e01-106">入力</span><span class="sxs-lookup"><span data-stu-id="01e01-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="01e01-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="01e01-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="01e01-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="01e01-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="01e01-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="01e01-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="01e01-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="01e01-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="01e01-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="01e01-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="01e01-112">`true` が以下の場合 `a` にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="01e01-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="01e01-113">解説</span><span class="sxs-lookup"><span data-stu-id="01e01-113">Remarks</span></span>

<span data-ttu-id="01e01-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="01e01-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```