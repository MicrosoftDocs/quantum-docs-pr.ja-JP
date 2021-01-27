---
uid: Microsoft.Quantum.Logical.Or
title: Or 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 4a29b7684b28b904b43ccceb8e63280999690349
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848477"
---
# <a name="or-function"></a><span data-ttu-id="fe00c-102">Or 関数</span><span class="sxs-lookup"><span data-stu-id="fe00c-102">Or function</span></span>

<span data-ttu-id="fe00c-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fe00c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fe00c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe00c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe00c-105">2つの値の論理和を返します。</span><span class="sxs-lookup"><span data-stu-id="fe00c-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="fe00c-106">入力</span><span class="sxs-lookup"><span data-stu-id="fe00c-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="fe00c-107">a: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fe00c-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fe00c-108">考慮される最初の値。</span><span class="sxs-lookup"><span data-stu-id="fe00c-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="fe00c-109">b: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fe00c-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fe00c-110">考慮する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="fe00c-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fe00c-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fe00c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fe00c-112">`true``a`またはのいずれか `b` がの場合にのみ `true` 。</span><span class="sxs-lookup"><span data-stu-id="fe00c-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe00c-113">解説</span><span class="sxs-lookup"><span data-stu-id="fe00c-113">Remarks</span></span>

<span data-ttu-id="fe00c-114">演算子とは異なり `or` 、この関数はショートサーキットではなく、両方の入力が完全に評価されます。</span><span class="sxs-lookup"><span data-stu-id="fe00c-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="fe00c-115">ショートサーキットの動作は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fe00c-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a or b;
let x = Or(a, b);
```