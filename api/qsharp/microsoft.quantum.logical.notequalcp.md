---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 81dd998353f674d55afe85dd20904047391bdb40
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720739"
---
# <a name="notequalcp-function"></a><span data-ttu-id="f799a-102">NotEqualCP 関数</span><span class="sxs-lookup"><span data-stu-id="f799a-102">NotEqualCP function</span></span>

<span data-ttu-id="f799a-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f799a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f799a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f799a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f799a-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="f799a-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="f799a-106">入力</span><span class="sxs-lookup"><span data-stu-id="f799a-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="f799a-107">a: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="f799a-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="f799a-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="f799a-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="f799a-109">b: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="f799a-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="f799a-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="f799a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f799a-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f799a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f799a-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="f799a-112">`true` if and only if `a` is not equal to `b`.</span></span>