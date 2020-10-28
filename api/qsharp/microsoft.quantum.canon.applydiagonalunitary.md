---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: ApplyDiagonalUnitary 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 6ecacf6e4fe2c505036de208c8aeb5350e479e3c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718286"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="456b4-102">ApplyDiagonalUnitary 操作</span><span class="sxs-lookup"><span data-stu-id="456b4-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="456b4-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="456b4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="456b4-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="456b4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="456b4-105">複雑なフェーズの配列を、qubits のレジスタの数値ベースの状態に適用します。</span><span class="sxs-lookup"><span data-stu-id="456b4-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="456b4-106">説明</span><span class="sxs-lookup"><span data-stu-id="456b4-106">Description</span></span>

<span data-ttu-id="456b4-107">この操作では、$n $ qubit number $ \ket{j} $ に $e ^ {i \ theta_j} $ という複雑なフェーズを適用する斜線を実装します。</span><span class="sxs-lookup"><span data-stu-id="456b4-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="456b4-108">特に、この操作は、ユニタリで表すことができます。</span><span class="sxs-lookup"><span data-stu-id="456b4-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="456b4-109">$ $ \begin{align} U = \ sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="456b4-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="456b4-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="456b4-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="456b4-111">入力</span><span class="sxs-lookup"><span data-stu-id="456b4-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="456b4-112">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="456b4-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="456b4-113">$ 2 ^ n $ 係数 $ \ theta_j $ までの配列。</span><span class="sxs-lookup"><span data-stu-id="456b4-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="456b4-114">$J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="456b4-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="456b4-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="456b4-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="456b4-116">数値の状態をリトルエンディアン形式でエンコードする $-qubit コントロールレジスタ $n ます。</span><span class="sxs-lookup"><span data-stu-id="456b4-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="456b4-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="456b4-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="456b4-118">解説</span><span class="sxs-lookup"><span data-stu-id="456b4-118">Remarks</span></span>

<span data-ttu-id="456b4-119">`coefficients` $ 2 ^ n $ 未満の値が指定されている場合は、$ \ theta_j = $0.0 という要素が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="456b4-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="456b4-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="456b4-120">References</span></span>

- <span data-ttu-id="456b4-121">クォンタムロジック回線の合成、Shende、Stephen、Igor、igor または Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="456b4-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="456b4-122">参照</span><span class="sxs-lookup"><span data-stu-id="456b4-122">See Also</span></span>

- [<span data-ttu-id="456b4-123">Microsoft. ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="456b4-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)