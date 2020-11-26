---
uid: Microsoft.Quantum.Logical.EqualC
title: EqualC 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualC
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 4c511489888613d95adaf154c005b3211af75446
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198386"
---
# <a name="equalc-function"></a><span data-ttu-id="6fcb0-102">EqualC 関数</span><span class="sxs-lookup"><span data-stu-id="6fcb0-102">EqualC function</span></span>

<span data-ttu-id="6fcb0-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6fcb0-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6fcb0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6fcb0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6fcb0-105">2つの入力が等しい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="6fcb0-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="6fcb0-106">入力</span><span class="sxs-lookup"><span data-stu-id="6fcb0-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="6fcb0-107">a: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="6fcb0-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="6fcb0-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="6fcb0-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="6fcb0-109">b: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="6fcb0-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="6fcb0-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="6fcb0-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6fcb0-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6fcb0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6fcb0-112">`true``a`がに等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="6fcb0-112">`true` if and only if `a` is equal to `b`.</span></span>