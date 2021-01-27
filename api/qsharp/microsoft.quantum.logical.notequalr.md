---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848496"
---
# <a name="notequalr-function"></a><span data-ttu-id="87598-102">NotEqualR 関数</span><span class="sxs-lookup"><span data-stu-id="87598-102">NotEqualR function</span></span>

<span data-ttu-id="87598-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="87598-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="87598-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="87598-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="87598-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="87598-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="87598-106">入力</span><span class="sxs-lookup"><span data-stu-id="87598-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="87598-107">a:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="87598-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="87598-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="87598-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="87598-109">b:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="87598-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="87598-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="87598-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="87598-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="87598-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="87598-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="87598-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="87598-113">解説</span><span class="sxs-lookup"><span data-stu-id="87598-113">Remarks</span></span>

<span data-ttu-id="87598-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="87598-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```