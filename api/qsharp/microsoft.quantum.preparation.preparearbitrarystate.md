---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: PrepareArbitraryState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 18f45da601b02fc5f83936b086323e31a66fc20b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724044"
---
# <a name="preparearbitrarystate-operation"></a><span data-ttu-id="9d01e-102">PrepareArbitraryState 操作</span><span class="sxs-lookup"><span data-stu-id="9d01e-102">PrepareArbitraryState operation</span></span>

<span data-ttu-id="9d01e-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="9d01e-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="9d01e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9d01e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9d01e-105">係数とリトルエンディアンでエンコードされたクォンタムレジスタを指定すると、は、指定された係数によって記述されるレジスタに状態を準備します。</span><span class="sxs-lookup"><span data-stu-id="9d01e-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="9d01e-106">説明</span><span class="sxs-lookup"><span data-stu-id="9d01e-106">Description</span></span>

<span data-ttu-id="9d01e-107">この操作では $n、_j e ^ {i t_j} $ から \ket{\psi} $-qubit コンピューティングベースの状態 $ \ket{0/cドット 0} $ から、複雑な $r 係数を持つ任意のクォンタム状態 $ $ を準備します。</span><span class="sxs-lookup"><span data-stu-id="9d01e-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="9d01e-108">具体的には、この操作のアクションは、すべてゼロの状態を処理するための $U $ として、</span><span class="sxs-lookup"><span data-stu-id="9d01e-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="9d01e-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\ sqrt_ \ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="9d01e-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="9d01e-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9d01e-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="9d01e-111">入力</span><span class="sxs-lookup"><span data-stu-id="9d01e-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="9d01e-112">係数: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="9d01e-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="9d01e-113">絶対値とフェーズ $ (r_j、t_j) $ で表される、最大 $ 2 ^ n $ の複合係数の配列。</span><span class="sxs-lookup"><span data-stu-id="9d01e-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="9d01e-114">$J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="9d01e-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="9d01e-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9d01e-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9d01e-116">リトルエンディアン形式での qubit レジスタのエンコード番号の状態。</span><span class="sxs-lookup"><span data-stu-id="9d01e-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="9d01e-117">この値は、コンピューティングベースの状態 $ \ket{0...0} $ で初期化されることが想定されています。</span><span class="sxs-lookup"><span data-stu-id="9d01e-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d01e-118">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d01e-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9d01e-119">解説</span><span class="sxs-lookup"><span data-stu-id="9d01e-119">Remarks</span></span>

<span data-ttu-id="9d01e-120">負の入力係数 $r _j < $0 は、値 $ | r_j | $ を持つ正の値として処理されます。</span><span class="sxs-lookup"><span data-stu-id="9d01e-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="9d01e-121">`coefficients` $ 2 ^ n $ 未満の場合は、要素 $ (r_j、t_j) = (0.0, 0.0) $ が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="9d01e-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="9d01e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d01e-122">References</span></span>

- <span data-ttu-id="9d01e-123">クォンタムロジック回線の合成、Shende、Stephen、Igor、igor または Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="9d01e-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="9d01e-124">参照</span><span class="sxs-lookup"><span data-stu-id="9d01e-124">See Also</span></span>

- [<span data-ttu-id="9d01e-125">ApproximatelyPrepareArbitraryState の準備</span><span class="sxs-lookup"><span data-stu-id="9d01e-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)