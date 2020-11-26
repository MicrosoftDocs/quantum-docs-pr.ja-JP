---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Measure 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: 804ae72ed2d5302b14011b737b7ed3ad2b9a14ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212292"
---
# <a name="measure-operation"></a><span data-ttu-id="1dd19-102">Measure 操作</span><span class="sxs-lookup"><span data-stu-id="1dd19-102">Measure operation</span></span>

<span data-ttu-id="1dd19-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="1dd19-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="1dd19-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="1dd19-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1dd19-105">指定した基底クラスの1つ以上の qubits の結合測定を実行します。</span><span class="sxs-lookup"><span data-stu-id="1dd19-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="1dd19-106">出力結果は、ディストリビューションによって得られます。 \begin{align} \ Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{/psi \ mid | \ left (\ done + P_0/otimes P_ {N-1} > right) \ mid P_1 |-psi}、\end{align} where $P _i $ は、の $i $ th 要素、 `bases` where $N = \texttt{Length} (\texttt{bases}) $ となります。</span><span class="sxs-lookup"><span data-stu-id="1dd19-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="1dd19-107">つまり、測定された `Result` 測定効果の eigenvalue が $ (-1) ^ d $ であるように、測定値は $ $d $ を返します。</span><span class="sxs-lookup"><span data-stu-id="1dd19-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="1dd19-108">入力</span><span class="sxs-lookup"><span data-stu-id="1dd19-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="1dd19-109">ベース: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="1dd19-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="1dd19-110">各 qubit の最新の製品要素を示す single qubit の値の配列。</span><span class="sxs-lookup"><span data-stu-id="1dd19-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1dd19-111">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1dd19-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1dd19-112">測定する qubits のレジスタ。</span><span class="sxs-lookup"><span data-stu-id="1dd19-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="1dd19-113">出力:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="1dd19-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="1dd19-114">`Zero` $ + $1 eigenvalue が観測されている場合は、 `One` $-$1 eigenvalue が観測されている場合はです。</span><span class="sxs-lookup"><span data-stu-id="1dd19-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="1dd19-115">解説</span><span class="sxs-lookup"><span data-stu-id="1dd19-115">Remarks</span></span>

<span data-ttu-id="1dd19-116">Basis 配列と qubit 配列の長さが異なる場合、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1dd19-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>