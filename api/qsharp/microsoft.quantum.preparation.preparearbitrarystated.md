---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateD
title: PrepareArbitraryStateD 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 61f6614821951435828cd28edeb1447cb33f3648
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842368"
---
# <a name="preparearbitrarystated-operation"></a><span data-ttu-id="13a32-102">PrepareArbitraryStateD 操作</span><span class="sxs-lookup"><span data-stu-id="13a32-102">PrepareArbitraryStateD operation</span></span>

<span data-ttu-id="13a32-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="13a32-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="13a32-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13a32-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13a32-105">係数とリトルエンディアンでエンコードされたクォンタムレジスタを指定すると、は、指定された係数によって記述されるレジスタに状態を準備します。</span><span class="sxs-lookup"><span data-stu-id="13a32-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryStateD (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="13a32-106">説明</span><span class="sxs-lookup"><span data-stu-id="13a32-106">Description</span></span>

<span data-ttu-id="13a32-107">この操作では $n、_j e ^ {i t_j} $ から \ket{\psi} $-qubit コンピューティングベースの状態 $ \ket{0/cドット 0} $ から、複雑な $r 係数を持つ任意のクォンタム状態 $ $ を準備します。</span><span class="sxs-lookup"><span data-stu-id="13a32-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="13a32-108">特に、この操作のアクションは、すべてゼロの状態を表す $ $U $ として、次のように処理することによってシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="13a32-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ that acts on the all-zeros state as</span></span>

<span data-ttu-id="13a32-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\ sqrt_ \ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="13a32-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="13a32-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="13a32-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="13a32-111">入力</span><span class="sxs-lookup"><span data-stu-id="13a32-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="13a32-112">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="13a32-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="13a32-113">最大 $ 2 ^ n $ 実数係数の配列。</span><span class="sxs-lookup"><span data-stu-id="13a32-113">Array of up to $2^n$ real coefficients.</span></span> <span data-ttu-id="13a32-114">$J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="13a32-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="13a32-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="13a32-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="13a32-116">リトルエンディアン形式での qubit レジスタのエンコード番号の状態。</span><span class="sxs-lookup"><span data-stu-id="13a32-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="13a32-117">この値は、コンピューティングベースの状態 $ \ket{0...0} $ で初期化されることが想定されています。</span><span class="sxs-lookup"><span data-stu-id="13a32-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="13a32-118">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="13a32-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="13a32-119">解説</span><span class="sxs-lookup"><span data-stu-id="13a32-119">Remarks</span></span>

<span data-ttu-id="13a32-120">負の入力係数 $r _j < $0 は、値 $ | r_j | $ を持つ正の値として処理されます。</span><span class="sxs-lookup"><span data-stu-id="13a32-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="13a32-121">`coefficients` $ 2 ^ n $ 未満の場合は、要素 $ (r_j、t_j) = (0.0, 0.0) $ が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="13a32-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="13a32-122">References</span><span class="sxs-lookup"><span data-stu-id="13a32-122">References</span></span>

- <span data-ttu-id="13a32-123">クォンタムロジック回線の合成、Shende、Stephen、Igor、igor または Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="13a32-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="13a32-124">参照</span><span class="sxs-lookup"><span data-stu-id="13a32-124">See Also</span></span>

- [<span data-ttu-id="13a32-125">ApproximatelyPrepareArbitraryState の準備</span><span class="sxs-lookup"><span data-stu-id="13a32-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)