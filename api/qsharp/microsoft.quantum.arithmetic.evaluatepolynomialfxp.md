---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: EvaluatePolynomialFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 3903bf69d5b0a6e57530f2c6a44e1d351c8a605f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721183"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="67512-102">EvaluatePolynomialFxP 操作</span><span class="sxs-lookup"><span data-stu-id="67512-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="67512-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="67512-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="67512-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="67512-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="67512-105">固定小数点表現で多項式を評価します。</span><span class="sxs-lookup"><span data-stu-id="67512-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="67512-106">入力</span><span class="sxs-lookup"><span data-stu-id="67512-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="67512-107">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="67512-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="67512-108">2番目の配列としての多項式の係数。つまり、配列 $ [a_0, a_1,..., a_d] $ (多項式の $P (x) = a_0 + a_1 x + \ cドット + a_d x ^ d $)。</span><span class="sxs-lookup"><span data-stu-id="67512-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="67512-109">fpx: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="67512-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="67512-110">多項式を評価する固定小数点数を入力します。</span><span class="sxs-lookup"><span data-stu-id="67512-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="67512-111">結果: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="67512-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="67512-112">$P (x) $ を保持する固定小数点数を出力します。</span><span class="sxs-lookup"><span data-stu-id="67512-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="67512-113">最初は、状態が $ \ket $ である必要があり {0} ます。</span><span class="sxs-lookup"><span data-stu-id="67512-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="67512-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67512-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

