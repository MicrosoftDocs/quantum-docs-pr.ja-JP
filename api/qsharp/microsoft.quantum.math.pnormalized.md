---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 196bdab67528aa8672a010ac3830459e27276ce9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227524"
---
# <a name="pnormalized-function"></a><span data-ttu-id="7647a-102">PNormalized 関数</span><span class="sxs-lookup"><span data-stu-id="7647a-102">PNormalized function</span></span>

<span data-ttu-id="7647a-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7647a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7647a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7647a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7647a-105">標準でのベクトルを正規化 `Double` `L(p)` します。</span><span class="sxs-lookup"><span data-stu-id="7647a-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="7647a-106">つまり、$ $x 型の配列を指定すると、 `Double[]` すべての要素が $p $-基準 $ x _p $ で除算された配列が返され \| \| ます。</span><span class="sxs-lookup"><span data-stu-id="7647a-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="7647a-107">入力</span><span class="sxs-lookup"><span data-stu-id="7647a-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="7647a-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7647a-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7647a-109">指数は、$p $-基準で $ $p ます。</span><span class="sxs-lookup"><span data-stu-id="7647a-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="7647a-110">array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7647a-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="7647a-111">出力: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7647a-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7647a-112">配列は、$-$p $ x _p $ で $x $ 正規化されて \| \| います。</span><span class="sxs-lookup"><span data-stu-id="7647a-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="7647a-113">参照</span><span class="sxs-lookup"><span data-stu-id="7647a-113">See Also</span></span>

- [<span data-ttu-id="7647a-114">Microsoft. Quantum.</span><span class="sxs-lookup"><span data-stu-id="7647a-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)