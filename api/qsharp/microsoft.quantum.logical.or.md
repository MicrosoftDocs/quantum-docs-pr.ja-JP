---
uid: Microsoft.Quantum.Logical.Or
title: Or 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 7093d908696a8cfda6b5ef648f9dfafcfac97144
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197128"
---
# <a name="or-function"></a><span data-ttu-id="5bce2-102">Or 関数</span><span class="sxs-lookup"><span data-stu-id="5bce2-102">Or function</span></span>

<span data-ttu-id="5bce2-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5bce2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5bce2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5bce2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5bce2-105">2つの値の論理和を返します。</span><span class="sxs-lookup"><span data-stu-id="5bce2-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="5bce2-106">入力</span><span class="sxs-lookup"><span data-stu-id="5bce2-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="5bce2-107">a: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5bce2-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5bce2-108">考慮される最初の値。</span><span class="sxs-lookup"><span data-stu-id="5bce2-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="5bce2-109">b: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5bce2-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5bce2-110">考慮する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="5bce2-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5bce2-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5bce2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5bce2-112">`true``a`またはのいずれか `b` がの場合にのみ `true` 。</span><span class="sxs-lookup"><span data-stu-id="5bce2-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5bce2-113">解説</span><span class="sxs-lookup"><span data-stu-id="5bce2-113">Remarks</span></span>

<span data-ttu-id="5bce2-114">演算子とは異なり `or` 、この関数はショートサーキットではなく、両方の入力が完全に評価されます。</span><span class="sxs-lookup"><span data-stu-id="5bce2-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="5bce2-115">ショートサーキットの動作は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5bce2-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```