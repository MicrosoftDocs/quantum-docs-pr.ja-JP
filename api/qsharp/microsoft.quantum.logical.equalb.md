---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: b566f5ba8548eadeecf63a1e91956d936e7e9a20
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198471"
---
# <a name="equalb-function"></a><span data-ttu-id="68dde-102">EqualB 関数</span><span class="sxs-lookup"><span data-stu-id="68dde-102">EqualB function</span></span>

<span data-ttu-id="68dde-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="68dde-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="68dde-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68dde-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68dde-105">2つの入力が等しい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="68dde-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="68dde-106">入力</span><span class="sxs-lookup"><span data-stu-id="68dde-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="68dde-107">a: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="68dde-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="68dde-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="68dde-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="68dde-109">b: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="68dde-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="68dde-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="68dde-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="68dde-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="68dde-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="68dde-112">`true``a`がに等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="68dde-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="68dde-113">解説</span><span class="sxs-lookup"><span data-stu-id="68dde-113">Remarks</span></span>

<span data-ttu-id="68dde-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="68dde-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```