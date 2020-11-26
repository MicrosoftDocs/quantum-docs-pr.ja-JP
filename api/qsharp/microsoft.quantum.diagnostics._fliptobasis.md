---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: 1581a1267902ceee81d6f01348f4ee718e49ee47
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223988"
---
# <a name="_fliptobasis-operation"></a><span data-ttu-id="10ef8-102">_flipToBasis 操作</span><span class="sxs-lookup"><span data-stu-id="10ef8-102">_flipToBasis operation</span></span>

<span data-ttu-id="10ef8-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="10ef8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="10ef8-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="10ef8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="10ef8-105">$ \Ket {0} \otimes\cdots\ket {0} $ を $ \ket{\ psi_0} \ otimes \ket{\ psi_ {n-1}} $ にマップする unitaries 適用します。 $ \ket{\ psi_k} $ は、に依存 `basis[k]` します。</span><span class="sxs-lookup"><span data-stu-id="10ef8-105">Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.</span></span>

<span data-ttu-id="10ef8-106">`basis[k]`と $ \ket{\ psi_k} $ の値の対応は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="10ef8-106">The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:</span></span>

- <span data-ttu-id="10ef8-107">`basis[k]=0` $ \rightarrow \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="10ef8-107">`basis[k]=0` $\rightarrow \ket{0}$.</span></span>
- <span data-ttu-id="10ef8-108">`basis[k]=1` $ \rightarrow \ket {1} $。</span><span class="sxs-lookup"><span data-stu-id="10ef8-108">`basis[k]=1` $\rightarrow \ket{1}$.</span></span>
- <span data-ttu-id="10ef8-109">`basis[k]=2` $ \rightarrow \ket{+} $。</span><span class="sxs-lookup"><span data-stu-id="10ef8-109">`basis[k]=2` $\rightarrow \ket{+}$.</span></span>
- <span data-ttu-id="10ef8-110">`basis[k]=3` $ \rightarrow \ket{i} $ (+ 1 eigenstate of P# li Y)。</span><span class="sxs-lookup"><span data-stu-id="10ef8-110">`basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).</span></span>

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="10ef8-111">入力</span><span class="sxs-lookup"><span data-stu-id="10ef8-111">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="10ef8-112">ベース: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="10ef8-112">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="10ef8-113">Qubit の各要素に1つずつ、単一の qubit basis 状態 Id の配列 (0 <= id <= 3)。</span><span class="sxs-lookup"><span data-stu-id="10ef8-113">Array of single-qubit basis state IDs (0 <= id <= 3), one for each element of qubits.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="10ef8-114">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="10ef8-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="10ef8-115">操作する qubit。</span><span class="sxs-lookup"><span data-stu-id="10ef8-115">Qubit to be operated on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="10ef8-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10ef8-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

