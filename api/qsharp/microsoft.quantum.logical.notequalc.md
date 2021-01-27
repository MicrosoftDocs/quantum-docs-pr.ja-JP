---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 33049b09405529bd418ff8652b6cb0f11bf734f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849064"
---
# <a name="notequalc-function"></a><span data-ttu-id="8f012-102">NotEqualC 関数</span><span class="sxs-lookup"><span data-stu-id="8f012-102">NotEqualC function</span></span>

<span data-ttu-id="8f012-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8f012-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8f012-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f012-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f012-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="8f012-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="8f012-106">入力</span><span class="sxs-lookup"><span data-stu-id="8f012-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="8f012-107">a: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="8f012-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="8f012-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="8f012-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="8f012-109">b: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="8f012-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="8f012-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="8f012-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8f012-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8f012-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8f012-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="8f012-112">`true` if and only if `a` is not equal to `b`.</span></span>