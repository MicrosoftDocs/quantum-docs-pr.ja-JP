---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: d52da4092f16d43ab9d08b03f798a4d6789c7348
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721195"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="0e44f-102">EvaluateOddPolynomialFxP 操作</span><span class="sxs-lookup"><span data-stu-id="0e44f-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="0e44f-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0e44f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0e44f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e44f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e44f-105">固定小数点表現で奇数の多項式を評価します。</span><span class="sxs-lookup"><span data-stu-id="0e44f-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="0e44f-106">入力</span><span class="sxs-lookup"><span data-stu-id="0e44f-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="0e44f-107">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0e44f-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0e44f-108">奇数多項式の係数 (配列 $ [a_0, a_1,..., a_k] $、奇数多項式の $P (x) = a_0 x + a_1 x ^ 3 + \ cドット + a_k x ^ {2k + 1} $) の2つの配列。</span><span class="sxs-lookup"><span data-stu-id="0e44f-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="0e44f-109">fpx: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="0e44f-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="0e44f-110">多項式を評価する固定小数点数を入力します。</span><span class="sxs-lookup"><span data-stu-id="0e44f-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="0e44f-111">結果: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="0e44f-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="0e44f-112">P (x) を保持する固定小数点数を出力します。</span><span class="sxs-lookup"><span data-stu-id="0e44f-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="0e44f-113">最初は、状態が $ \ket $ である必要があり {0} ます。</span><span class="sxs-lookup"><span data-stu-id="0e44f-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e44f-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e44f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

