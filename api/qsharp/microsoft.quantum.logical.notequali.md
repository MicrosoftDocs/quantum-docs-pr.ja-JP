---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f88ae08f45c284f65151419c214705c74c3fadac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814505"
---
# <a name="notequali-function"></a><span data-ttu-id="f1e9a-102">NotEqualI 関数</span><span class="sxs-lookup"><span data-stu-id="f1e9a-102">NotEqualI function</span></span>

<span data-ttu-id="f1e9a-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f1e9a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f1e9a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1e9a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1e9a-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="f1e9a-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="f1e9a-106">入力</span><span class="sxs-lookup"><span data-stu-id="f1e9a-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="f1e9a-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f1e9a-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f1e9a-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="f1e9a-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="f1e9a-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f1e9a-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f1e9a-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="f1e9a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f1e9a-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f1e9a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f1e9a-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="f1e9a-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1e9a-113">解説</span><span class="sxs-lookup"><span data-stu-id="f1e9a-113">Remarks</span></span>

<span data-ttu-id="f1e9a-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f1e9a-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualI(a, b);
```