---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 68e0e105a6b3742ec11e80ff92c39578a786aa85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709830"
---
# <a name="notequali-function"></a><span data-ttu-id="9c187-102">NotEqualI 関数</span><span class="sxs-lookup"><span data-stu-id="9c187-102">NotEqualI function</span></span>

<span data-ttu-id="9c187-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="9c187-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="9c187-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c187-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c187-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="9c187-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="9c187-106">入力</span><span class="sxs-lookup"><span data-stu-id="9c187-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="9c187-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c187-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9c187-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="9c187-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="9c187-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c187-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9c187-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="9c187-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9c187-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9c187-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9c187-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="9c187-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c187-113">解説</span><span class="sxs-lookup"><span data-stu-id="9c187-113">Remarks</span></span>

<span data-ttu-id="9c187-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9c187-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```