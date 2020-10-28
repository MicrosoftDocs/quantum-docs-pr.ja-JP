---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: c8ee7e6a04cc2478f1c97fcc1d964a1574f7b1fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720758"
---
# <a name="equalcp-function"></a><span data-ttu-id="32a81-102">EqualCP 関数</span><span class="sxs-lookup"><span data-stu-id="32a81-102">EqualCP function</span></span>

<span data-ttu-id="32a81-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="32a81-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="32a81-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="32a81-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="32a81-105">2つの入力が等しい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="32a81-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="32a81-106">入力</span><span class="sxs-lookup"><span data-stu-id="32a81-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="32a81-107">a: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="32a81-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="32a81-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="32a81-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="32a81-109">b: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="32a81-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="32a81-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="32a81-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="32a81-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="32a81-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="32a81-112">`true``a`がに等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="32a81-112">`true` if and only if `a` is equal to `b`.</span></span>