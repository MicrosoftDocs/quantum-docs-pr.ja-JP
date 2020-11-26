---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: コンピューターの Procalfxp 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: 3ca050d6ce9daaa10e14c2f12dd571398cf436b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223393"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="b470a-102">コンピューターの Procalfxp 操作</span><span class="sxs-lookup"><span data-stu-id="b470a-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="b470a-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b470a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b470a-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="b470a-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="b470a-105">$ 1/x $ を計算します (固定小数点数 $x $)。</span><span class="sxs-lookup"><span data-stu-id="b470a-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b470a-106">入力</span><span class="sxs-lookup"><span data-stu-id="b470a-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="b470a-107">x: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b470a-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b470a-108">反転する固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="b470a-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="b470a-109">結果: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b470a-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b470a-110">結果を保持する固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="b470a-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="b470a-111">$ \Ket{0.0} $ に初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b470a-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b470a-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b470a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

