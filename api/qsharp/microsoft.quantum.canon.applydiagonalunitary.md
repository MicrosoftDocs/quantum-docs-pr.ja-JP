---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: ApplyDiagonalUnitary 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 14ab8d7beddda26594967225934d472d52bac9eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841888"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="5365e-102">ApplyDiagonalUnitary 操作</span><span class="sxs-lookup"><span data-stu-id="5365e-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="5365e-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5365e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5365e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5365e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5365e-105">複雑なフェーズの配列を、qubits のレジスタの数値ベースの状態に適用します。</span><span class="sxs-lookup"><span data-stu-id="5365e-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="5365e-106">説明</span><span class="sxs-lookup"><span data-stu-id="5365e-106">Description</span></span>

<span data-ttu-id="5365e-107">この操作では、$n $ qubit number $ \ket{j} $ に $e ^ {i \ theta_j} $ という複雑なフェーズを適用する斜線を実装します。</span><span class="sxs-lookup"><span data-stu-id="5365e-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="5365e-108">特に、この操作は、ユニタリで表すことができます。</span><span class="sxs-lookup"><span data-stu-id="5365e-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="5365e-109">$ $ \begin{align} U = \ sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="5365e-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="5365e-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="5365e-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="5365e-111">入力</span><span class="sxs-lookup"><span data-stu-id="5365e-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="5365e-112">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5365e-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="5365e-113">$ 2 ^ n $ 係数 $ \ theta_j $ までの配列。</span><span class="sxs-lookup"><span data-stu-id="5365e-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="5365e-114">$J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="5365e-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="5365e-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5365e-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5365e-116">数値の状態をリトルエンディアン形式でエンコードする $-qubit コントロールレジスタ $n ます。</span><span class="sxs-lookup"><span data-stu-id="5365e-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5365e-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5365e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5365e-118">解説</span><span class="sxs-lookup"><span data-stu-id="5365e-118">Remarks</span></span>

<span data-ttu-id="5365e-119">`coefficients` $ 2 ^ n $ 未満の値が指定されている場合は、$ \ theta_j = $0.0 という要素が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="5365e-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="5365e-120">References</span><span class="sxs-lookup"><span data-stu-id="5365e-120">References</span></span>

- <span data-ttu-id="5365e-121">クォンタムロジック回線の合成、Shende、Stephen、Igor、igor または Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="5365e-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="5365e-122">参照</span><span class="sxs-lookup"><span data-stu-id="5365e-122">See Also</span></span>

- [<span data-ttu-id="5365e-123">Microsoft. ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="5365e-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)