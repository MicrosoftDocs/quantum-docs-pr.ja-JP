---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: PrepareArbitraryState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > PrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 18a1e86f8e110a8f48d7dd50961e1f1f471ffc4e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190702"
---
# <a name="preparearbitrarystate-operation"></a><span data-ttu-id="e1994-102">PrepareArbitraryState 操作</span><span class="sxs-lookup"><span data-stu-id="e1994-102">PrepareArbitraryState operation</span></span>

<span data-ttu-id="e1994-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e1994-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e1994-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1994-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="e1994-105">PrepareArbitraryState は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="e1994-105">PrepareArbitraryState has been deprecated.</span></span> <span data-ttu-id="e1994-106">代わりに、<xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="e1994-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="e1994-107">係数とリトルエンディアンでエンコードされたクォンタムレジスタを指定すると、は、指定された係数によって記述されるレジスタに状態を準備します。</span><span class="sxs-lookup"><span data-stu-id="e1994-107">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e1994-108">説明</span><span class="sxs-lookup"><span data-stu-id="e1994-108">Description</span></span>

<span data-ttu-id="e1994-109">この操作では $n、_j e ^ {i t_j} $ から \ket{\psi} $-qubit コンピューティングベースの状態 $ \ket{0/cドット 0} $ から、複雑な $r 係数を持つ任意のクォンタム状態 $ $ を準備します。</span><span class="sxs-lookup"><span data-stu-id="e1994-109">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="e1994-110">具体的には、この操作のアクションは、すべてゼロの状態を処理するための $U $ として、</span><span class="sxs-lookup"><span data-stu-id="e1994-110">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="e1994-111">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\ sqrt_ \ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="e1994-111">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="e1994-112">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="e1994-112">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="e1994-113">入力</span><span class="sxs-lookup"><span data-stu-id="e1994-113">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="e1994-114">係数: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="e1994-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="e1994-115">絶対値とフェーズ $ (r_j、t_j) $ で表される、最大 $ 2 ^ n $ の複合係数の配列。</span><span class="sxs-lookup"><span data-stu-id="e1994-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="e1994-116">$J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="e1994-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="e1994-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e1994-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e1994-118">リトルエンディアン形式での qubit レジスタのエンコード番号の状態。</span><span class="sxs-lookup"><span data-stu-id="e1994-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="e1994-119">この値は、コンピューティングベースの状態 $ \ket{0...0} $ で初期化されることが想定されています。</span><span class="sxs-lookup"><span data-stu-id="e1994-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1994-120">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1994-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e1994-121">解説</span><span class="sxs-lookup"><span data-stu-id="e1994-121">Remarks</span></span>

<span data-ttu-id="e1994-122">負の入力係数 $r _j < $0 は、値 $ | r_j | $ を持つ正の値として処理されます。</span><span class="sxs-lookup"><span data-stu-id="e1994-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="e1994-123">`coefficients` $ 2 ^ n $ 未満の場合は、要素 $ (r_j、t_j) = (0.0, 0.0) $ が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="e1994-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="e1994-124">リファレンス</span><span class="sxs-lookup"><span data-stu-id="e1994-124">References</span></span>

- <span data-ttu-id="e1994-125">クォンタムロジック回線の合成、Shende、Stephen、Igor、igor または Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="e1994-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="e1994-126">参照</span><span class="sxs-lookup"><span data-stu-id="e1994-126">See Also</span></span>

- [<span data-ttu-id="e1994-127">ApproximatelyPrepareArbitraryState の準備</span><span class="sxs-lookup"><span data-stu-id="e1994-127">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)