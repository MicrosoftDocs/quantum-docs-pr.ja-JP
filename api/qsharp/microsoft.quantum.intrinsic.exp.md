---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Exp 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 2eea29ec08260ea9cee1bafde80a0942e06f5abc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212411"
---
# <a name="exp-operation"></a><span data-ttu-id="fc582-102">Exp 操作</span><span class="sxs-lookup"><span data-stu-id="fc582-102">Exp operation</span></span>

<span data-ttu-id="fc582-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="fc582-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="fc582-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="fc582-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fc582-105">マルチ qubit の P# li 演算子の指数を適用します。</span><span class="sxs-lookup"><span data-stu-id="fc582-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="fc582-106">\begin{align} e ^ {i/シータ [P_0/otimes P_1/cドット P_ {N-1}]}, \end{align} ここで $P _i $ はの $i $ th 要素、 `paulis` where $N = $ `Length(paulis)` です。</span><span class="sxs-lookup"><span data-stu-id="fc582-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fc582-107">入力</span><span class="sxs-lookup"><span data-stu-id="fc582-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="fc582-108">paulis: [p li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="fc582-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="fc582-109">各 qubit の最新の製品要素を示す single qubit の値の配列。</span><span class="sxs-lookup"><span data-stu-id="fc582-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="fc582-110">シータ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fc582-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fc582-111">ターゲットレジスタのローテーションに使用する、指定されたマルチ qubit の P# li 演算子に関する角度。</span><span class="sxs-lookup"><span data-stu-id="fc582-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="fc582-112">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fc582-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fc582-113">指定された回転をに適用するために登録します。</span><span class="sxs-lookup"><span data-stu-id="fc582-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fc582-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc582-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

