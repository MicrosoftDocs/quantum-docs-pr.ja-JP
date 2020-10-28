---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725220"
---
# <a name="decomposedon-function"></a><span data-ttu-id="ef044-102">DecomposedOn 関数</span><span class="sxs-lookup"><span data-stu-id="ef044-102">DecomposedOn function</span></span>

<span data-ttu-id="ef044-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ef044-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ef044-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ef044-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ef044-105">分解され変数の順列の並べ替え</span><span class="sxs-lookup"><span data-stu-id="ef044-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="ef044-106">説明</span><span class="sxs-lookup"><span data-stu-id="ef044-106">Description</span></span>

<span data-ttu-id="ef044-107">順列 $ \ pi $ ( `perm` ) とインデックス $i $ () に指定されてい `index` ます。このメソッドは3つの順列 $ ((\ pi_l, \ pi_r), \ pi ') $ を返します。 $ \ pi_l $ と $ \ pi_r $ のイメージでは、要素内の要素のビットを変更しないようにして、$-pi ' $ のイメージは、要素内でビット $i $ を変更しないようにします。</span><span class="sxs-lookup"><span data-stu-id="ef044-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="ef044-108">入力</span><span class="sxs-lookup"><span data-stu-id="ef044-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="ef044-109">perm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ef044-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="ef044-110">index: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ef044-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="ef044-111">出力: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="ef044-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

