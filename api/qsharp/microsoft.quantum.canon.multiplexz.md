---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: MultiplexZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: f7b1973e18ad396ebe892ad63ae47374a7cafbd5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715780"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="ad4f9-102">MultiplexZ 操作</span><span class="sxs-lookup"><span data-stu-id="ad4f9-102">MultiplexZ operation</span></span>

<span data-ttu-id="ad4f9-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ad4f9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ad4f9-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ad4f9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ad4f9-105">Qubits の配列で条件付きの Pan Li Z の回転条件を適用します。</span><span class="sxs-lookup"><span data-stu-id="ad4f9-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="ad4f9-106">説明</span><span class="sxs-lookup"><span data-stu-id="ad4f9-106">Description</span></span>

<span data-ttu-id="ad4f9-107">これは、$n $ qubit number $ \ket{j} $ によって制御されている場合に、single qubit p Li operator $Z $ の角度 $ \ theta_j $ によって回転を実行する、制御された数値の乗算操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="ad4f9-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="ad4f9-108">特に、この操作は、ユニタリで表すことができます。</span><span class="sxs-lookup"><span data-stu-id="ad4f9-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="ad4f9-109">$ $ \begin{align} U = \ sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}/otimes e ^ {i Z \ theta_j}。</span><span class="sxs-lookup"><span data-stu-id="ad4f9-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="ad4f9-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="ad4f9-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="ad4f9-111">入力</span><span class="sxs-lookup"><span data-stu-id="ad4f9-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="ad4f9-112">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ad4f9-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ad4f9-113">$ 2 ^ n $ 係数 $ \ theta_j $ までの配列。</span><span class="sxs-lookup"><span data-stu-id="ad4f9-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="ad4f9-114">$J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="ad4f9-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="ad4f9-115">control: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ad4f9-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ad4f9-116">数値の状態をリトルエンディアン形式でエンコードする $-qubit コントロールレジスタ $n ます。</span><span class="sxs-lookup"><span data-stu-id="ad4f9-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ad4f9-117">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ad4f9-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ad4f9-118">$E ^ {i P \ theta_j} $ によって回転された1つの qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="ad4f9-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad4f9-119">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad4f9-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ad4f9-120">解説</span><span class="sxs-lookup"><span data-stu-id="ad4f9-120">Remarks</span></span>

<span data-ttu-id="ad4f9-121">`coefficients` $ 2 ^ n $ 未満の値が指定されている場合は、$ \ theta_j = $0.0 という要素が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="ad4f9-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="ad4f9-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad4f9-122">References</span></span>

- <span data-ttu-id="ad4f9-123">クォンタムロジック回線の合成、Shende、Stephen、Igor、igor または Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="ad4f9-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="ad4f9-124">参照</span><span class="sxs-lookup"><span data-stu-id="ad4f9-124">See Also</span></span>

- [<span data-ttu-id="ad4f9-125">Microsoft. ApproximatelyMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="ad4f9-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)