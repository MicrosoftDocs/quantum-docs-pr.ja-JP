---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 8b3d4cceb69619ed32977337fc0fe7401db38cbd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211051"
---
# <a name="bitsizel-function"></a><span data-ttu-id="90bd4-102">BitSizeL 関数</span><span class="sxs-lookup"><span data-stu-id="90bd4-102">BitSizeL function</span></span>

<span data-ttu-id="90bd4-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="90bd4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="90bd4-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90bd4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90bd4-105">負でない整数の場合 `a` 、はを表すために必要なビット数を返し `a` ます。</span><span class="sxs-lookup"><span data-stu-id="90bd4-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="90bd4-106">つまり、$a < 2 ^ n $ である $n $ の最小値を返します。</span><span class="sxs-lookup"><span data-stu-id="90bd4-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="90bd4-107">入力</span><span class="sxs-lookup"><span data-stu-id="90bd4-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="90bd4-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="90bd4-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="90bd4-109">ビットサイズを計算する整数。</span><span class="sxs-lookup"><span data-stu-id="90bd4-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="90bd4-110">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90bd4-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90bd4-111">のビットサイズ `a` 。</span><span class="sxs-lookup"><span data-stu-id="90bd4-111">The bit-size of `a`.</span></span>