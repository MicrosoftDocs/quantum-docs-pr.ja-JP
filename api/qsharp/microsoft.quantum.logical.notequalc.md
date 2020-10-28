---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: b26ad3515cb801b122858b9474aea76a0e5c498b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709821"
---
# <a name="notequalc-function"></a><span data-ttu-id="27b68-102">NotEqualC 関数</span><span class="sxs-lookup"><span data-stu-id="27b68-102">NotEqualC function</span></span>

<span data-ttu-id="27b68-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="27b68-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="27b68-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27b68-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27b68-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="27b68-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="27b68-106">入力</span><span class="sxs-lookup"><span data-stu-id="27b68-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="27b68-107">a: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="27b68-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="27b68-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="27b68-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="27b68-109">b: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="27b68-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="27b68-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="27b68-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="27b68-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="27b68-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="27b68-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="27b68-112">`true` if and only if `a` is not equal to `b`.</span></span>