---
uid: Microsoft.Quantum.Logical.And
title: And 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 6c405bdb4182cc7f32bd04952dec25a974c03445
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849240"
---
# <a name="and-function"></a><span data-ttu-id="a2881-102">And 関数</span><span class="sxs-lookup"><span data-stu-id="a2881-102">And function</span></span>

<span data-ttu-id="a2881-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a2881-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a2881-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2881-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2881-105">2つの値のブール値の組み合わせを返します。</span><span class="sxs-lookup"><span data-stu-id="a2881-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="a2881-106">入力</span><span class="sxs-lookup"><span data-stu-id="a2881-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="a2881-107">a: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a2881-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a2881-108">考慮される最初の値。</span><span class="sxs-lookup"><span data-stu-id="a2881-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="a2881-109">b: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a2881-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a2881-110">考慮する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="a2881-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a2881-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a2881-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a2881-112">`true``a`と `b` の両方がである場合にのみ `true` 。</span><span class="sxs-lookup"><span data-stu-id="a2881-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2881-113">解説</span><span class="sxs-lookup"><span data-stu-id="a2881-113">Remarks</span></span>

<span data-ttu-id="a2881-114">演算子とは異なり `and` 、この関数はショートサーキットではなく、両方の入力が完全に評価されます。</span><span class="sxs-lookup"><span data-stu-id="a2881-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="a2881-115">ショートサーキットの動作は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a2881-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a and b;
let x = And(a, b);
```