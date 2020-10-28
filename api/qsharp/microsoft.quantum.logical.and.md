---
uid: Microsoft.Quantum.Logical.And
title: And 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720799"
---
# <a name="and-function"></a><span data-ttu-id="a7c96-102">And 関数</span><span class="sxs-lookup"><span data-stu-id="a7c96-102">And function</span></span>

<span data-ttu-id="a7c96-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a7c96-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a7c96-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a7c96-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a7c96-105">2つの値のブール値の組み合わせを返します。</span><span class="sxs-lookup"><span data-stu-id="a7c96-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="a7c96-106">入力</span><span class="sxs-lookup"><span data-stu-id="a7c96-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="a7c96-107">a: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a7c96-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a7c96-108">考慮される最初の値。</span><span class="sxs-lookup"><span data-stu-id="a7c96-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="a7c96-109">b: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a7c96-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a7c96-110">考慮する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="a7c96-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a7c96-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a7c96-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a7c96-112">`true``a`と `b` の両方がである場合にのみ `true` 。</span><span class="sxs-lookup"><span data-stu-id="a7c96-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a7c96-113">解説</span><span class="sxs-lookup"><span data-stu-id="a7c96-113">Remarks</span></span>

<span data-ttu-id="a7c96-114">演算子とは異なり `and` 、この関数はショートサーキットではなく、両方の入力が完全に評価されます。</span><span class="sxs-lookup"><span data-stu-id="a7c96-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="a7c96-115">ショートサーキットの動作は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a7c96-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```