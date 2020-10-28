---
uid: Microsoft.Quantum.Logical.EqualD
title: EqualD 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 024ddee785a6a907b4a39d0eccc5990b4c5d5d83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711398"
---
# <a name="equald-function"></a><span data-ttu-id="bc748-102">EqualD 関数</span><span class="sxs-lookup"><span data-stu-id="bc748-102">EqualD function</span></span>

<span data-ttu-id="bc748-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="bc748-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="bc748-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc748-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc748-105">2つの入力が等しい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="bc748-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="bc748-106">入力</span><span class="sxs-lookup"><span data-stu-id="bc748-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="bc748-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bc748-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bc748-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="bc748-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="bc748-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bc748-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bc748-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="bc748-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bc748-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bc748-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bc748-112">`true``a`がに等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="bc748-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc748-113">解説</span><span class="sxs-lookup"><span data-stu-id="bc748-113">Remarks</span></span>

<span data-ttu-id="bc748-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="bc748-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```