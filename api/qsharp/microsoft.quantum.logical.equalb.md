---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 91ab51180018a9b95a2f9010477c0a24f3a54617
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720782"
---
# <a name="equalb-function"></a><span data-ttu-id="7e88e-102">EqualB 関数</span><span class="sxs-lookup"><span data-stu-id="7e88e-102">EqualB function</span></span>

<span data-ttu-id="7e88e-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7e88e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7e88e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e88e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e88e-105">2つの入力が等しい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="7e88e-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="7e88e-106">入力</span><span class="sxs-lookup"><span data-stu-id="7e88e-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="7e88e-107">a: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7e88e-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7e88e-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="7e88e-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="7e88e-109">b: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7e88e-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7e88e-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="7e88e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7e88e-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7e88e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7e88e-112">`true``a`がに等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="7e88e-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e88e-113">解説</span><span class="sxs-lookup"><span data-stu-id="7e88e-113">Remarks</span></span>

<span data-ttu-id="7e88e-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="7e88e-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```