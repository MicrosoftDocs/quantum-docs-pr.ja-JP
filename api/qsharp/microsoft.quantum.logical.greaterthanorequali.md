---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0435aae4a824bd19d972e9f6b331260bbe21f692
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197791"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="2d123-102">GreaterThanOrEqualI 関数</span><span class="sxs-lookup"><span data-stu-id="2d123-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="2d123-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2d123-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2d123-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d123-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d123-105">数値がもう1つの数値以上の場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="2d123-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="2d123-106">入力</span><span class="sxs-lookup"><span data-stu-id="2d123-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="2d123-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2d123-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2d123-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="2d123-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="2d123-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2d123-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2d123-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="2d123-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2d123-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2d123-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2d123-112">`true``a`がより大きいか、またはと等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="2d123-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d123-113">解説</span><span class="sxs-lookup"><span data-stu-id="2d123-113">Remarks</span></span>

<span data-ttu-id="2d123-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2d123-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```