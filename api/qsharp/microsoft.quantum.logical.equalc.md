---
uid: Microsoft.Quantum.Logical.EqualC
title: EqualC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualC
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 8b0c34915ef392e8a84706f601da71f3848a3134
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720770"
---
# <a name="equalc-function"></a><span data-ttu-id="bf5e4-102">EqualC 関数</span><span class="sxs-lookup"><span data-stu-id="bf5e4-102">EqualC function</span></span>

<span data-ttu-id="bf5e4-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="bf5e4-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="bf5e4-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bf5e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bf5e4-105">2つの入力が等しい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="bf5e4-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="bf5e4-106">入力</span><span class="sxs-lookup"><span data-stu-id="bf5e4-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="bf5e4-107">a: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="bf5e4-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="bf5e4-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="bf5e4-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="bf5e4-109">b: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="bf5e4-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="bf5e4-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="bf5e4-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bf5e4-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bf5e4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bf5e4-112">`true``a`がに等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="bf5e4-112">`true` if and only if `a` is equal to `b`.</span></span>