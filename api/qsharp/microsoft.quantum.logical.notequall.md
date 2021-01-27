---
uid: Microsoft.Quantum.Logical.NotEqualL
title: 注 Quall 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: b19de2e4e8052c77118f341700357b212e20af53
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849024"
---
# <a name="notequall-function"></a><span data-ttu-id="b2e7e-102">注 Quall 関数</span><span class="sxs-lookup"><span data-stu-id="b2e7e-102">NotEqualL function</span></span>

<span data-ttu-id="b2e7e-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b2e7e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b2e7e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2e7e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2e7e-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="b2e7e-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="b2e7e-106">入力</span><span class="sxs-lookup"><span data-stu-id="b2e7e-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="b2e7e-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b2e7e-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b2e7e-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="b2e7e-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="b2e7e-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b2e7e-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b2e7e-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="b2e7e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b2e7e-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b2e7e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b2e7e-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="b2e7e-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2e7e-113">解説</span><span class="sxs-lookup"><span data-stu-id="b2e7e-113">Remarks</span></span>

<span data-ttu-id="b2e7e-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b2e7e-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualL(a, b);
```