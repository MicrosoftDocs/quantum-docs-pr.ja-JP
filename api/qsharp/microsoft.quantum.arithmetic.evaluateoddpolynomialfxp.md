---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 852e986cd09c3b2e31263f53e381d9da73298415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846662"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="88a0e-102">EvaluateOddPolynomialFxP 操作</span><span class="sxs-lookup"><span data-stu-id="88a0e-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="88a0e-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="88a0e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="88a0e-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="88a0e-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="88a0e-105">固定小数点表現で奇数の多項式を評価します。</span><span class="sxs-lookup"><span data-stu-id="88a0e-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="88a0e-106">入力</span><span class="sxs-lookup"><span data-stu-id="88a0e-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="88a0e-107">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="88a0e-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="88a0e-108">奇数多項式の係数 (配列 $ [a_0, a_1,..., a_k] $、奇数多項式の $P (x) = a_0 x + a_1 x ^ 3 + \ cドット + a_k x ^ {2k + 1} $) の2つの配列。</span><span class="sxs-lookup"><span data-stu-id="88a0e-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="88a0e-109">fpx: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="88a0e-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="88a0e-110">多項式を評価する固定小数点数を入力します。</span><span class="sxs-lookup"><span data-stu-id="88a0e-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="88a0e-111">結果: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="88a0e-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="88a0e-112">P (x) を保持する固定小数点数を出力します。</span><span class="sxs-lookup"><span data-stu-id="88a0e-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="88a0e-113">最初は、状態が $ \ket $ である必要があり {0} ます。</span><span class="sxs-lookup"><span data-stu-id="88a0e-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="88a0e-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="88a0e-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

