---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195853"
---
# <a name="bitsizei-function"></a><span data-ttu-id="11de3-102">BitSizeI 関数</span><span class="sxs-lookup"><span data-stu-id="11de3-102">BitSizeI function</span></span>

<span data-ttu-id="11de3-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="11de3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="11de3-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="11de3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="11de3-105">負でない整数の場合 `a` 、はを表すために必要なビット数を返し `a` ます。</span><span class="sxs-lookup"><span data-stu-id="11de3-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="11de3-106">つまり、$a < 2 ^ n $ である $n $ の最小値を返します。</span><span class="sxs-lookup"><span data-stu-id="11de3-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="11de3-107">入力</span><span class="sxs-lookup"><span data-stu-id="11de3-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="11de3-108">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="11de3-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="11de3-109">ビットサイズを計算する整数。</span><span class="sxs-lookup"><span data-stu-id="11de3-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="11de3-110">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="11de3-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="11de3-111">のビットサイズ `a` 。</span><span class="sxs-lookup"><span data-stu-id="11de3-111">The bit-size of `a`.</span></span>