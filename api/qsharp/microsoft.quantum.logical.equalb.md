---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 2a15a749f52fe814db4fa57118f69c80fa22158a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817253"
---
# <a name="equalb-function"></a><span data-ttu-id="511a4-102">EqualB 関数</span><span class="sxs-lookup"><span data-stu-id="511a4-102">EqualB function</span></span>

<span data-ttu-id="511a4-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="511a4-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="511a4-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="511a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="511a4-105">2つの入力が等しい場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="511a4-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="511a4-106">入力</span><span class="sxs-lookup"><span data-stu-id="511a4-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="511a4-107">a: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="511a4-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="511a4-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="511a4-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="511a4-109">b: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="511a4-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="511a4-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="511a4-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="511a4-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="511a4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="511a4-112">`true``a`がに等しい場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="511a4-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="511a4-113">解説</span><span class="sxs-lookup"><span data-stu-id="511a4-113">Remarks</span></span>

<span data-ttu-id="511a4-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="511a4-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualB(a, b);
```