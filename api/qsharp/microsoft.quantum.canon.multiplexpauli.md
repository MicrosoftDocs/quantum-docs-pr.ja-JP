---
uid: Microsoft.Quantum.Canon.MultiplexPauli
title: 乗数操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits.
ms.openlocfilehash: 0714e796c1e5ad097814bcf507f49f59a844e9ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715785"
---
# <a name="multiplexpauli-operation"></a><span data-ttu-id="81ca8-102">乗数操作</span><span class="sxs-lookup"><span data-stu-id="81ca8-102">MultiplexPauli operation</span></span>

<span data-ttu-id="81ca8-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="81ca8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="81ca8-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81ca8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81ca8-105">Qubits の配列に条件付きの回転を適用します。</span><span class="sxs-lookup"><span data-stu-id="81ca8-105">Applies a Pauli rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexPauli (coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="81ca8-106">説明</span><span class="sxs-lookup"><span data-stu-id="81ca8-106">Description</span></span>

<span data-ttu-id="81ca8-107">これは、$n $ qubit number $ \ket{j} $ によって制御されている場合に、single qubit p Li operator $P $ の角度 $ \ theta_j $ によって回転を実行する、多重制御された、乗算操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="81ca8-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="81ca8-108">特に、この操作のアクションは、ユニタリによって表されます。</span><span class="sxs-lookup"><span data-stu-id="81ca8-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="81ca8-109">$ $ \begin{align} U = \ sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}/otimes e ^ {i P \ theta_j}。</span><span class="sxs-lookup"><span data-stu-id="81ca8-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="81ca8-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="81ca8-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="81ca8-111">入力</span><span class="sxs-lookup"><span data-stu-id="81ca8-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="81ca8-112">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="81ca8-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="81ca8-113">$ 2 ^ n $ 係数 $ \ theta_j $ までの配列。</span><span class="sxs-lookup"><span data-stu-id="81ca8-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="81ca8-114">$J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="81ca8-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="81ca8-115">p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li</span><span class="sxs-lookup"><span data-stu-id="81ca8-115">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="81ca8-116">回転の軸を決定する p$P li 演算子。</span><span class="sxs-lookup"><span data-stu-id="81ca8-116">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="81ca8-117">control: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="81ca8-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="81ca8-118">数値の状態をリトルエンディアン形式でエンコードする $-qubit コントロールレジスタ $n ます。</span><span class="sxs-lookup"><span data-stu-id="81ca8-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="81ca8-119">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="81ca8-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="81ca8-120">$E ^ {i P \ theta_j} $ によって回転された1つの qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="81ca8-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81ca8-121">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81ca8-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="81ca8-122">解説</span><span class="sxs-lookup"><span data-stu-id="81ca8-122">Remarks</span></span>

<span data-ttu-id="81ca8-123">`coefficients` $ 2 ^ n $ 未満の値が指定されている場合は、$ \ theta_j = $0.0 という要素が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="81ca8-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="81ca8-124">参照</span><span class="sxs-lookup"><span data-stu-id="81ca8-124">See Also</span></span>

- [<span data-ttu-id="81ca8-125">Microsoft. ApproximatelyMultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="81ca8-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli)