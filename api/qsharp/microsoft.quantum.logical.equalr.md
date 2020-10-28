---
uid: Microsoft.Quantum.Logical.EqualR
title: EqualR 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710031"
---
# <a name="equalr-function"></a><span data-ttu-id="09a2e-102">EqualR 関数</span><span class="sxs-lookup"><span data-stu-id="09a2e-102">EqualR function</span></span>

<span data-ttu-id="09a2e-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="09a2e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="09a2e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="09a2e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="09a2e-105">2つの入力が等しい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="09a2e-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="09a2e-106">入力</span><span class="sxs-lookup"><span data-stu-id="09a2e-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="09a2e-107">a: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="09a2e-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="09a2e-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="09a2e-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="09a2e-109">b: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="09a2e-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="09a2e-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="09a2e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="09a2e-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="09a2e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="09a2e-112">`true``a`がに等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="09a2e-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="09a2e-113">解説</span><span class="sxs-lookup"><span data-stu-id="09a2e-113">Remarks</span></span>

<span data-ttu-id="09a2e-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="09a2e-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```