---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722285"
---
# <a name="pnormalized-function"></a><span data-ttu-id="44b48-102">PNormalized 関数</span><span class="sxs-lookup"><span data-stu-id="44b48-102">PNormalized function</span></span>

<span data-ttu-id="44b48-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="44b48-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="44b48-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="44b48-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="44b48-105">標準でのベクトルを正規化 `Double` `L(p)` します。</span><span class="sxs-lookup"><span data-stu-id="44b48-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="44b48-106">つまり、$ $x 型の配列を指定すると、 `Double[]` すべての要素が $p $-基準 $ x _p $ で除算された配列が返され \| \| ます。</span><span class="sxs-lookup"><span data-stu-id="44b48-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="44b48-107">入力</span><span class="sxs-lookup"><span data-stu-id="44b48-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="44b48-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="44b48-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="44b48-109">指数は、$p $-基準で $ $p ます。</span><span class="sxs-lookup"><span data-stu-id="44b48-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="44b48-110">array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="44b48-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="44b48-111">出力: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="44b48-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="44b48-112">配列は、$-$p $ x _p $ で $x $ 正規化されて \| \| います。</span><span class="sxs-lookup"><span data-stu-id="44b48-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="44b48-113">参照</span><span class="sxs-lookup"><span data-stu-id="44b48-113">See Also</span></span>

- [<span data-ttu-id="44b48-114">Microsoft. Quantum.</span><span class="sxs-lookup"><span data-stu-id="44b48-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)