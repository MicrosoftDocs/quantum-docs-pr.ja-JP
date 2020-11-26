---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 0be2c97ec7b0350fc20eace76746f3ffff65fd52
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197366"
---
# <a name="notequalc-function"></a><span data-ttu-id="e303e-102">NotEqualC 関数</span><span class="sxs-lookup"><span data-stu-id="e303e-102">NotEqualC function</span></span>

<span data-ttu-id="e303e-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e303e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e303e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e303e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e303e-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="e303e-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="e303e-106">入力</span><span class="sxs-lookup"><span data-stu-id="e303e-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="e303e-107">a: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="e303e-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="e303e-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="e303e-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="e303e-109">b: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="e303e-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="e303e-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="e303e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e303e-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e303e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e303e-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="e303e-112">`true` if and only if `a` is not equal to `b`.</span></span>