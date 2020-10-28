---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: ApproximatelyMultiplexPauli 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: c91937d9e82a2a1514d81529adb35a5f804a0e13
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716816"
---
# <a name="approximatelymultiplexpauli-operation"></a><span data-ttu-id="d6e07-102">ApproximatelyMultiplexPauli 操作</span><span class="sxs-lookup"><span data-stu-id="d6e07-102">ApproximatelyMultiplexPauli operation</span></span>

<span data-ttu-id="d6e07-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d6e07-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d6e07-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d6e07-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d6e07-105">Qubits の配列で条件付きの回転を適用し、指定された許容範囲に従って小さな回転角度を切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="d6e07-105">Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="d6e07-106">説明</span><span class="sxs-lookup"><span data-stu-id="d6e07-106">Description</span></span>

<span data-ttu-id="d6e07-107">これは、$n $ qubit number $ \ket{j} $ によって制御されている場合に、single qubit p Li operator $P $ の角度 $ \ theta_j $ によって回転を実行する、多重制御された、乗算操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="d6e07-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="d6e07-108">特に、この操作のアクションは、ユニタリによって表されます。</span><span class="sxs-lookup"><span data-stu-id="d6e07-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="d6e07-109">$ $ \begin{align} U = \ sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}/otimes e ^ {i P \ theta_j}。</span><span class="sxs-lookup"><span data-stu-id="d6e07-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="d6e07-110">\end{align}</span><span class="sxs-lookup"><span data-stu-id="d6e07-110">\end{align}</span></span>

##

## <a name="input"></a><span data-ttu-id="d6e07-111">入力</span><span class="sxs-lookup"><span data-stu-id="d6e07-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="d6e07-112">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d6e07-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d6e07-113">小さい係数が切り捨てられる公差。</span><span class="sxs-lookup"><span data-stu-id="d6e07-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="d6e07-114">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d6e07-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d6e07-115">$ 2 ^ n $ 係数 $ \ theta_j $ までの配列。</span><span class="sxs-lookup"><span data-stu-id="d6e07-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="d6e07-116">$J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="d6e07-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="d6e07-117">p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li</span><span class="sxs-lookup"><span data-stu-id="d6e07-117">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="d6e07-118">回転の軸を決定する p$P li 演算子。</span><span class="sxs-lookup"><span data-stu-id="d6e07-118">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="d6e07-119">control: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d6e07-119">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d6e07-120">数値の状態をリトルエンディアン形式でエンコードする $-qubit コントロールレジスタ $n ます。</span><span class="sxs-lookup"><span data-stu-id="d6e07-120">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d6e07-121">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d6e07-121">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d6e07-122">$E ^ {i P \ theta_j} $ によって回転された1つの qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="d6e07-122">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d6e07-123">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6e07-123">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d6e07-124">解説</span><span class="sxs-lookup"><span data-stu-id="d6e07-124">Remarks</span></span>

<span data-ttu-id="d6e07-125">`coefficients` $ 2 ^ n $ 未満の値が指定されている場合は、$ \ theta_j = $0.0 という要素が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="d6e07-125">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6e07-126">参照</span><span class="sxs-lookup"><span data-stu-id="d6e07-126">See Also</span></span>

- [<span data-ttu-id="d6e07-127">Microsoft. Canon....</span><span class="sxs-lookup"><span data-stu-id="d6e07-127">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)