---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState
title: ApproximatelyPrepareArbitraryState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 2561b098c5faf2d24bb9ab348fb052025808e441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724086"
---
# <a name="approximatelypreparearbitrarystate-operation"></a><span data-ttu-id="f13d7-102">ApproximatelyPrepareArbitraryState 操作</span><span class="sxs-lookup"><span data-stu-id="f13d7-102">ApproximatelyPrepareArbitraryState operation</span></span>

<span data-ttu-id="f13d7-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f13d7-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f13d7-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f13d7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f13d7-105">係数とリトルエンディアンでエンコードされたクォンタムレジスタを指定すると、は指定された係数によって示されるレジスタの状態を、指定された近似値に設定します。</span><span class="sxs-lookup"><span data-stu-id="f13d7-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryState (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="f13d7-106">説明</span><span class="sxs-lookup"><span data-stu-id="f13d7-106">Description</span></span>

<span data-ttu-id="f13d7-107">この操作では $n、_j e ^ {i t_j} $ から \ket{\psi} $-qubit コンピューティングベースの状態 $ \ket{0/cドット 0} $ から、複雑な $r 係数を持つ任意のクォンタム状態 $ $ を準備します。</span><span class="sxs-lookup"><span data-stu-id="f13d7-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="f13d7-108">具体的には、この操作のアクションは、すべてゼロの状態を処理するための $U $ として、</span><span class="sxs-lookup"><span data-stu-id="f13d7-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="f13d7-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\ sqrt_ \ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="f13d7-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="f13d7-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f13d7-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="f13d7-111">入力</span><span class="sxs-lookup"><span data-stu-id="f13d7-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="f13d7-112">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f13d7-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f13d7-113">指定された状態を準備するときに使用する近似の許容範囲。</span><span class="sxs-lookup"><span data-stu-id="f13d7-113">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="f13d7-114">係数: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="f13d7-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="f13d7-115">絶対値とフェーズ $ (r_j、t_j) $ で表される、最大 $ 2 ^ n $ の複合係数の配列。</span><span class="sxs-lookup"><span data-stu-id="f13d7-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="f13d7-116">$J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="f13d7-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f13d7-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f13d7-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f13d7-118">リトルエンディアン形式での qubit レジスタのエンコード番号の状態。</span><span class="sxs-lookup"><span data-stu-id="f13d7-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="f13d7-119">この値は、コンピューティングベースの状態 $ \ket{0...0} $ で初期化されることが想定されています。</span><span class="sxs-lookup"><span data-stu-id="f13d7-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f13d7-120">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f13d7-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f13d7-121">解説</span><span class="sxs-lookup"><span data-stu-id="f13d7-121">Remarks</span></span>

<span data-ttu-id="f13d7-122">負の入力係数 $r _j < $0 は、値 $ | r_j | $ を持つ正の値として処理されます。</span><span class="sxs-lookup"><span data-stu-id="f13d7-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="f13d7-123">`coefficients` $ 2 ^ n $ 未満の場合は、要素 $ (r_j、t_j) = (0.0, 0.0) $ が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="f13d7-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="f13d7-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="f13d7-124">References</span></span>

- <span data-ttu-id="f13d7-125">クォンタムロジック回線の合成、Shende、Stephen、Igor、igor または Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="f13d7-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="f13d7-126">参照</span><span class="sxs-lookup"><span data-stu-id="f13d7-126">See Also</span></span>

- [<span data-ttu-id="f13d7-127">ApproximatelyPrepareArbitraryState の準備</span><span class="sxs-lookup"><span data-stu-id="f13d7-127">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)