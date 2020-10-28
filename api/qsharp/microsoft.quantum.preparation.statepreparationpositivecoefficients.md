---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722896"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="0b063-102">StatePreparationPositiveCoefficients 関数</span><span class="sxs-lookup"><span data-stu-id="0b063-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="0b063-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="0b063-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="0b063-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b063-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b063-105">指定されたクォンタム状態を準備する操作を返します。</span><span class="sxs-lookup"><span data-stu-id="0b063-105">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="0b063-106">返された操作 $U $ は、$ \ket{0...0} $ という $n から正の係数 $ \ $0 alpha_j を含む任意のクォンタム状態 $ \ket{\psi} $ を準備します。</span><span class="sxs-lookup"><span data-stu-id="0b063-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="0b063-107">新しく割り当てられたレジスタの U のアクションは、$ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}} によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="0b063-107">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="0b063-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="0b063-108">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="0b063-109">入力</span><span class="sxs-lookup"><span data-stu-id="0b063-109">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="0b063-110">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0b063-110">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0b063-111">$ 2 ^ n $ 係数 $ \ alpha_j $ までの配列。</span><span class="sxs-lookup"><span data-stu-id="0b063-111">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="0b063-112">$J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="0b063-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="0b063-113">出力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0b063-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0b063-114">状態の準備のためのユニタリ操作 $U $ です。</span><span class="sxs-lookup"><span data-stu-id="0b063-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b063-115">解説</span><span class="sxs-lookup"><span data-stu-id="0b063-115">Remarks</span></span>

<span data-ttu-id="0b063-116">負の入力係数 $ \ alpha_j < $0 は、$ | \ alpha_j | $ という値を持つ正の値として処理されます。</span><span class="sxs-lookup"><span data-stu-id="0b063-116">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="0b063-117">`coefficients` $ 2 ^ n $ 未満の値が指定されている場合は、$ \ alpha_j = $0.0 という要素が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="0b063-117">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>