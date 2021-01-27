---
uid: Microsoft.Quantum.Logical.EqualI
title: EqualI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 87cf00ea8bb738cda30092b3d80940291beb1fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816746"
---
# <a name="equali-function"></a><span data-ttu-id="171c0-102">EqualI 関数</span><span class="sxs-lookup"><span data-stu-id="171c0-102">EqualI function</span></span>

<span data-ttu-id="171c0-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="171c0-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="171c0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="171c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="171c0-105">2つの入力が等しい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="171c0-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="171c0-106">入力</span><span class="sxs-lookup"><span data-stu-id="171c0-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="171c0-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="171c0-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="171c0-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="171c0-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="171c0-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="171c0-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="171c0-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="171c0-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="171c0-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="171c0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="171c0-112">`true``a`がに等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="171c0-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="171c0-113">解説</span><span class="sxs-lookup"><span data-stu-id="171c0-113">Remarks</span></span>

<span data-ttu-id="171c0-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="171c0-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualI(a, b);
```