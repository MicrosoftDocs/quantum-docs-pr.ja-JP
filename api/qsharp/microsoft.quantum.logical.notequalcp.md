---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 85225109a3822a9b63a231631f3d7265143418b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814397"
---
# <a name="notequalcp-function"></a><span data-ttu-id="2b470-102">NotEqualCP 関数</span><span class="sxs-lookup"><span data-stu-id="2b470-102">NotEqualCP function</span></span>

<span data-ttu-id="2b470-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2b470-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2b470-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b470-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b470-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="2b470-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="2b470-106">入力</span><span class="sxs-lookup"><span data-stu-id="2b470-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="2b470-107">a: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="2b470-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="2b470-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="2b470-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="2b470-109">b: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="2b470-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="2b470-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="2b470-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2b470-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2b470-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2b470-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="2b470-112">`true` if and only if `a` is not equal to `b`.</span></span>