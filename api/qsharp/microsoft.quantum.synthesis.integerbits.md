---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: 整数のビット関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719846"
---
# <a name="integerbits-function"></a><span data-ttu-id="6b1ad-102">整数のビット関数</span><span class="sxs-lookup"><span data-stu-id="6b1ad-102">IntegerBits function</span></span>

<span data-ttu-id="6b1ad-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6b1ad-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6b1ad-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6b1ad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6b1ad-105">整数のビットが設定されているすべての位置を返します。</span><span class="sxs-lookup"><span data-stu-id="6b1ad-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="6b1ad-106">入力</span><span class="sxs-lookup"><span data-stu-id="6b1ad-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="6b1ad-107">値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6b1ad-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6b1ad-108">負でない数値。</span><span class="sxs-lookup"><span data-stu-id="6b1ad-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="6b1ad-109">長さ: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6b1ad-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6b1ad-110">のバイナリ展開に含まれるビット数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="6b1ad-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="6b1ad-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6b1ad-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6b1ad-112">すべての `value` ビットが位置することを考慮 `length - 1` したバイナリ展開の1であるすべてのビット位置 (0 から始まる) を含む配列。</span><span class="sxs-lookup"><span data-stu-id="6b1ad-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="6b1ad-113">配列内のすべての位置は、位置によって昇順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="6b1ad-113">All positions are ordered in the array by position in an increasing order.</span></span>