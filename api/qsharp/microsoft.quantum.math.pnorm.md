---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194731"
---
# <a name="pnorm-function"></a><span data-ttu-id="22ddc-102">PNorm 関数</span><span class="sxs-lookup"><span data-stu-id="22ddc-102">PNorm function</span></span>

<span data-ttu-id="22ddc-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="22ddc-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="22ddc-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22ddc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22ddc-105">`L(p)`のベクトルの基準を返し `Double` ます。</span><span class="sxs-lookup"><span data-stu-id="22ddc-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="22ddc-106">つまり、$ $x 型の $ が指定されている場合、 `Double[]` $-$p $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $ が返されます。</span><span class="sxs-lookup"><span data-stu-id="22ddc-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="22ddc-107">入力</span><span class="sxs-lookup"><span data-stu-id="22ddc-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="22ddc-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="22ddc-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="22ddc-109">指数は、$p $-基準で $ $p ます。</span><span class="sxs-lookup"><span data-stu-id="22ddc-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="22ddc-110">array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="22ddc-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="22ddc-111">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="22ddc-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="22ddc-112">$P $-標準 $ \| x \| _p $。</span><span class="sxs-lookup"><span data-stu-id="22ddc-112">The $p$-norm $\|x\|_p$.</span></span>