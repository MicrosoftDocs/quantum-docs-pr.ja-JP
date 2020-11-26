---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dc132cbab556bd4b5d5c557ad267f1839e8039fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197213"
---
# <a name="notequali-function"></a><span data-ttu-id="72869-102">NotEqualI 関数</span><span class="sxs-lookup"><span data-stu-id="72869-102">NotEqualI function</span></span>

<span data-ttu-id="72869-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="72869-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="72869-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72869-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72869-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="72869-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="72869-106">入力</span><span class="sxs-lookup"><span data-stu-id="72869-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="72869-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72869-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72869-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="72869-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="72869-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72869-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72869-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="72869-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="72869-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="72869-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="72869-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="72869-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="72869-113">解説</span><span class="sxs-lookup"><span data-stu-id="72869-113">Remarks</span></span>

<span data-ttu-id="72869-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="72869-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```