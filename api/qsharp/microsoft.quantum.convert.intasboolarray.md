---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713456"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="22c18-102">IntAsBoolArray 関数</span><span class="sxs-lookup"><span data-stu-id="22c18-102">IntAsBoolArray function</span></span>

<span data-ttu-id="22c18-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="22c18-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="22c18-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22c18-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22c18-105">返された配列に対してリトルエンディアン表現を使用して、正の整数のバイナリ表現を生成します。</span><span class="sxs-lookup"><span data-stu-id="22c18-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="22c18-106">入力</span><span class="sxs-lookup"><span data-stu-id="22c18-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="22c18-107">数値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="22c18-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="22c18-108">ブール値の配列に変換する正の整数。</span><span class="sxs-lookup"><span data-stu-id="22c18-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="22c18-109">ビット: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="22c18-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="22c18-110">のバイナリ表現に含まれるビット数 `number` 。</span><span class="sxs-lookup"><span data-stu-id="22c18-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="22c18-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="22c18-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="22c18-112">を表すブール値の配列 `number` 。</span><span class="sxs-lookup"><span data-stu-id="22c18-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="22c18-113">解説</span><span class="sxs-lookup"><span data-stu-id="22c18-113">Remarks</span></span>

<span data-ttu-id="22c18-114">入力は `bits` 0 ~ 63 の範囲で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22c18-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="22c18-115">入力は `number` 0 から $ 2 ^ {\texttt{bits}}-$1 の間でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="22c18-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>