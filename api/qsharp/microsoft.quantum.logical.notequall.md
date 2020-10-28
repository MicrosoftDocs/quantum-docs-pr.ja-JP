---
uid: Microsoft.Quantum.Logical.NotEqualL
title: 注 Quall 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f1d36c284293519e75e6c30ac64679c7bdf4609c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709807"
---
# <a name="notequall-function"></a><span data-ttu-id="e24f6-102">注 Quall 関数</span><span class="sxs-lookup"><span data-stu-id="e24f6-102">NotEqualL function</span></span>

<span data-ttu-id="e24f6-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e24f6-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e24f6-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e24f6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e24f6-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="e24f6-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="e24f6-106">入力</span><span class="sxs-lookup"><span data-stu-id="e24f6-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="e24f6-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e24f6-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e24f6-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="e24f6-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="e24f6-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e24f6-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e24f6-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="e24f6-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e24f6-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e24f6-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e24f6-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="e24f6-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e24f6-113">解説</span><span class="sxs-lookup"><span data-stu-id="e24f6-113">Remarks</span></span>

<span data-ttu-id="e24f6-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e24f6-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```