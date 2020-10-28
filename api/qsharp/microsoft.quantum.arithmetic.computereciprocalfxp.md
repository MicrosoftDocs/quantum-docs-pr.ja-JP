---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: コンピューターの Procalfxp 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: e8f31d82fc69a3d7f4b571c4a679255dffc28b7f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721250"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="557a2-102">コンピューターの Procalfxp 操作</span><span class="sxs-lookup"><span data-stu-id="557a2-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="557a2-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="557a2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="557a2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="557a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="557a2-105">$ 1/x $ を計算します (固定小数点数 $x $)。</span><span class="sxs-lookup"><span data-stu-id="557a2-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="557a2-106">入力</span><span class="sxs-lookup"><span data-stu-id="557a2-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="557a2-107">x: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="557a2-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="557a2-108">反転する固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="557a2-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="557a2-109">結果: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="557a2-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="557a2-110">結果を保持する固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="557a2-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="557a2-111">$ \Ket{0.0} $ に初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="557a2-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="557a2-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="557a2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

