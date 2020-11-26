---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 40f059e49affbb1b5af7dc349f6ee53dfb357873
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197740"
---
# <a name="lessthand-function"></a><span data-ttu-id="cb5c1-102">LessThanD 関数</span><span class="sxs-lookup"><span data-stu-id="cb5c1-102">LessThanD function</span></span>

<span data-ttu-id="cb5c1-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cb5c1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cb5c1-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb5c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb5c1-105">数値が別の数値より小さい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="cb5c1-106">入力</span><span class="sxs-lookup"><span data-stu-id="cb5c1-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="cb5c1-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cb5c1-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cb5c1-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="cb5c1-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cb5c1-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cb5c1-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cb5c1-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cb5c1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cb5c1-112">`true``a`が厳密により小さい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb5c1-113">解説</span><span class="sxs-lookup"><span data-stu-id="cb5c1-113">Remarks</span></span>

<span data-ttu-id="cb5c1-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```