---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: dd934fde3fae9c1a43032b4b08ac03afa72798d1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709933"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="53d41-102">LessThanOrEqualI 関数</span><span class="sxs-lookup"><span data-stu-id="53d41-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="53d41-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="53d41-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="53d41-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53d41-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53d41-105">数値が別の数値以下の場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="53d41-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="53d41-106">入力</span><span class="sxs-lookup"><span data-stu-id="53d41-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="53d41-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53d41-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53d41-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="53d41-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="53d41-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53d41-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53d41-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="53d41-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="53d41-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="53d41-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="53d41-112">`true` が以下の場合 `a` にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="53d41-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="53d41-113">解説</span><span class="sxs-lookup"><span data-stu-id="53d41-113">Remarks</span></span>

<span data-ttu-id="53d41-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="53d41-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```