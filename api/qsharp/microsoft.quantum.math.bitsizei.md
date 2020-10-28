---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7cfe03908a8a394fc8ceb1c9facbf02f3db2d48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723195"
---
# <a name="bitsizei-function"></a><span data-ttu-id="785ac-102">BitSizeI 関数</span><span class="sxs-lookup"><span data-stu-id="785ac-102">BitSizeI function</span></span>

<span data-ttu-id="785ac-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="785ac-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="785ac-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="785ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="785ac-105">負でない整数の場合 `a` 、はを表すために必要なビット数を返し `a` ます。</span><span class="sxs-lookup"><span data-stu-id="785ac-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="785ac-106">つまり、$a < 2 ^ n $ である $n $ の最小値を返します。</span><span class="sxs-lookup"><span data-stu-id="785ac-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="785ac-107">入力</span><span class="sxs-lookup"><span data-stu-id="785ac-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="785ac-108">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="785ac-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="785ac-109">ビットサイズを計算する整数。</span><span class="sxs-lookup"><span data-stu-id="785ac-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="785ac-110">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="785ac-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="785ac-111">のビットサイズ `a` 。</span><span class="sxs-lookup"><span data-stu-id="785ac-111">The bit-size of `a`.</span></span>