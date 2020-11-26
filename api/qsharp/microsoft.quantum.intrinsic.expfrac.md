---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: 操作の実行
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 8ccea068dd61aaf8c1ba384969adef5644e8401e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198997"
---
# <a name="expfrac-operation"></a><span data-ttu-id="fe48a-102">操作の実行</span><span class="sxs-lookup"><span data-stu-id="fe48a-102">ExpFrac operation</span></span>

<span data-ttu-id="fe48a-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="fe48a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="fe48a-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="fe48a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fe48a-105">Dyadic の分数で指定された引数を使用して、マルチ qubit の P# li 演算子の指数を適用します。</span><span class="sxs-lookup"><span data-stu-id="fe48a-105">Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.</span></span>

<span data-ttu-id="fe48a-106">\begin{align} e ^ {i \ pi k [P_0/otimes P_1/cドット P_ {N-1}]/2 ^ N}、\end{align} where $P _i $ はの $i $ th 要素、 `paulis` where $N = $ `Length(paulis)` です。</span><span class="sxs-lookup"><span data-stu-id="fe48a-106">\begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fe48a-107">入力</span><span class="sxs-lookup"><span data-stu-id="fe48a-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="fe48a-108">paulis: [p li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="fe48a-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="fe48a-109">各 qubit の最新の製品要素を示す single qubit の値の配列。</span><span class="sxs-lookup"><span data-stu-id="fe48a-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="fe48a-110">分子: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fe48a-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fe48a-111">Qubit レジスタを回転する角度の、dyadic の分数表現の分子 ($k $)。</span><span class="sxs-lookup"><span data-stu-id="fe48a-111">Numerator ($k$) in the dyadic fraction representation of the angle by which the qubit register is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="fe48a-112">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fe48a-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fe48a-113">Qubit レジスタを回転する角度の分母を指定する2の累乗 ($n $)。</span><span class="sxs-lookup"><span data-stu-id="fe48a-113">Power of two ($n$) specifying the denominator of the angle by which the qubit register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="fe48a-114">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fe48a-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fe48a-115">指定された回転をに適用するために登録します。</span><span class="sxs-lookup"><span data-stu-id="fe48a-115">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fe48a-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe48a-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

