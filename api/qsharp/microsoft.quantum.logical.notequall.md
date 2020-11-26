---
uid: Microsoft.Quantum.Logical.NotEqualL
title: 注 Quall 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: e138a8def30bc77499662ffa6bc214d0c6a38893
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197230"
---
# <a name="notequall-function"></a><span data-ttu-id="f4f0f-102">注 Quall 関数</span><span class="sxs-lookup"><span data-stu-id="f4f0f-102">NotEqualL function</span></span>

<span data-ttu-id="f4f0f-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f4f0f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f4f0f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4f0f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4f0f-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="f4f0f-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="f4f0f-106">入力</span><span class="sxs-lookup"><span data-stu-id="f4f0f-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="f4f0f-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f4f0f-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f4f0f-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="f4f0f-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="f4f0f-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f4f0f-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f4f0f-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="f4f0f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f4f0f-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f4f0f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f4f0f-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="f4f0f-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4f0f-113">解説</span><span class="sxs-lookup"><span data-stu-id="f4f0f-113">Remarks</span></span>

<span data-ttu-id="f4f0f-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f4f0f-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```