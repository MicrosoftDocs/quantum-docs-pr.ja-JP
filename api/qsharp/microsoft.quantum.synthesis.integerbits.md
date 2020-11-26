---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: 整数のビット関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231094"
---
# <a name="integerbits-function"></a><span data-ttu-id="ceb2c-102">整数のビット関数</span><span class="sxs-lookup"><span data-stu-id="ceb2c-102">IntegerBits function</span></span>

<span data-ttu-id="ceb2c-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ceb2c-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ceb2c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ceb2c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ceb2c-105">整数のビットが設定されているすべての位置を返します。</span><span class="sxs-lookup"><span data-stu-id="ceb2c-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="ceb2c-106">入力</span><span class="sxs-lookup"><span data-stu-id="ceb2c-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="ceb2c-107">値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ceb2c-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ceb2c-108">負でない数値。</span><span class="sxs-lookup"><span data-stu-id="ceb2c-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="ceb2c-109">長さ: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ceb2c-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ceb2c-110">のバイナリ展開に含まれるビット数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="ceb2c-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="ceb2c-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ceb2c-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ceb2c-112">すべての `value` ビットが位置することを考慮 `length - 1` したバイナリ展開の1であるすべてのビット位置 (0 から始まる) を含む配列。</span><span class="sxs-lookup"><span data-stu-id="ceb2c-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="ceb2c-113">配列内のすべての位置は、位置によって昇順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="ceb2c-113">All positions are ordered in the array by position in an increasing order.</span></span>