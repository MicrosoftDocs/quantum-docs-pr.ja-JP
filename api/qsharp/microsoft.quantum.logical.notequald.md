---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4599d7125dbc67547af454183f620e8d84f2caf7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197247"
---
# <a name="notequald-function"></a><span data-ttu-id="235ff-102">NotEqualD 関数</span><span class="sxs-lookup"><span data-stu-id="235ff-102">NotEqualD function</span></span>

<span data-ttu-id="235ff-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="235ff-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="235ff-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="235ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="235ff-105">2つの入力が等しくない場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="235ff-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="235ff-106">入力</span><span class="sxs-lookup"><span data-stu-id="235ff-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="235ff-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="235ff-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="235ff-108">比較する最初の値。</span><span class="sxs-lookup"><span data-stu-id="235ff-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="235ff-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="235ff-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="235ff-110">比較する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="235ff-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="235ff-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="235ff-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="235ff-112">`true``a`がと等しくない場合にのみ `b` 。</span><span class="sxs-lookup"><span data-stu-id="235ff-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="235ff-113">解説</span><span class="sxs-lookup"><span data-stu-id="235ff-113">Remarks</span></span>

<span data-ttu-id="235ff-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="235ff-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```