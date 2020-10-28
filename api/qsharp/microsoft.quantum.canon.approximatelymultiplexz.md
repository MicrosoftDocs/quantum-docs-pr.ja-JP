---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: ApproximatelyMultiplexZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: ac5195b8b3afaad4d41fe50d45652644e2397e1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716793"
---
# <a name="approximatelymultiplexz-operation"></a><span data-ttu-id="09ea6-102">ApproximatelyMultiplexZ 操作</span><span class="sxs-lookup"><span data-stu-id="09ea6-102">ApproximatelyMultiplexZ operation</span></span>

<span data-ttu-id="09ea6-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="09ea6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="09ea6-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="09ea6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="09ea6-105">Qubits の配列に条件付きで条件付きの回転を適用し、指定された許容範囲に従って小さな回転角度を切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="09ea6-105">Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="09ea6-106">説明</span><span class="sxs-lookup"><span data-stu-id="09ea6-106">Description</span></span>

<span data-ttu-id="09ea6-107">これは、$n $ qubit number $ \ket{j} $ によって制御されている場合に、single qubit p Li operator $Z $ の角度 $ \ theta_j $ によって回転を実行する、制御された数値の乗算操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="09ea6-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="09ea6-108">特に、この操作は、ユニタリで表すことができます。</span><span class="sxs-lookup"><span data-stu-id="09ea6-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="09ea6-109">$ $ \begin{align} U = \ sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}/otimes e ^ {i Z \ theta_j}。</span><span class="sxs-lookup"><span data-stu-id="09ea6-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="09ea6-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="09ea6-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="09ea6-111">入力</span><span class="sxs-lookup"><span data-stu-id="09ea6-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="09ea6-112">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="09ea6-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="09ea6-113">小さい係数が切り捨てられる公差。</span><span class="sxs-lookup"><span data-stu-id="09ea6-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="09ea6-114">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="09ea6-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="09ea6-115">$ 2 ^ n $ 係数 $ \ theta_j $ までの配列。</span><span class="sxs-lookup"><span data-stu-id="09ea6-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="09ea6-116">$J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="09ea6-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="09ea6-117">control: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="09ea6-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="09ea6-118">数値の状態をリトルエンディアン形式でエンコードする $-qubit コントロールレジスタ $n ます。</span><span class="sxs-lookup"><span data-stu-id="09ea6-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="09ea6-119">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="09ea6-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="09ea6-120">$E ^ {i P \ theta_j} $ によって回転された1つの qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="09ea6-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="09ea6-121">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09ea6-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="09ea6-122">解説</span><span class="sxs-lookup"><span data-stu-id="09ea6-122">Remarks</span></span>

<span data-ttu-id="09ea6-123">`coefficients` $ 2 ^ n $ 未満の値が指定されている場合は、$ \ theta_j = $0.0 という要素が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="09ea6-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="09ea6-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="09ea6-124">References</span></span>

- <span data-ttu-id="09ea6-125">クォンタムロジック回線の合成、Shende、Stephen、Igor、igor または Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="09ea6-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="09ea6-126">参照</span><span class="sxs-lookup"><span data-stu-id="09ea6-126">See Also</span></span>

- [<span data-ttu-id="09ea6-127">Microsoft. MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="09ea6-127">Microsoft.Quantum.Canon.MultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.MultiplexZ)