---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: df735408f76eb6b88f0d867021d69b83edd69b7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197298"
---
# <a name="notequalcp-function"></a><span data-ttu-id="dfe8b-102">NotEqualCP 関数</span><span class="sxs-lookup"><span data-stu-id="dfe8b-102">NotEqualCP function</span></span>

<span data-ttu-id="dfe8b-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="dfe8b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="dfe8b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dfe8b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dfe8b-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="dfe8b-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="dfe8b-106">入力</span><span class="sxs-lookup"><span data-stu-id="dfe8b-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="dfe8b-107">a: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="dfe8b-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="dfe8b-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="dfe8b-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="dfe8b-109">b: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="dfe8b-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="dfe8b-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="dfe8b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="dfe8b-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dfe8b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dfe8b-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="dfe8b-112">`true` if and only if `a` is not equal to `b`.</span></span>