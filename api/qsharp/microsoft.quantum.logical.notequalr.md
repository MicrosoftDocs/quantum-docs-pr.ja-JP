---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4ac6cf4b220fa42c8eb946d6fbcad4cdb191afcd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197196"
---
# <a name="notequalr-function"></a><span data-ttu-id="ec8ce-102">NotEqualR 関数</span><span class="sxs-lookup"><span data-stu-id="ec8ce-102">NotEqualR function</span></span>

<span data-ttu-id="ec8ce-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ec8ce-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ec8ce-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec8ce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec8ce-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="ec8ce-106">入力</span><span class="sxs-lookup"><span data-stu-id="ec8ce-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="ec8ce-107">a:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="ec8ce-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="ec8ce-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="ec8ce-109">b:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="ec8ce-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="ec8ce-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ec8ce-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ec8ce-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ec8ce-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ec8ce-113">解説</span><span class="sxs-lookup"><span data-stu-id="ec8ce-113">Remarks</span></span>

<span data-ttu-id="ec8ce-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```