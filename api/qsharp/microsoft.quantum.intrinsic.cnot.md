---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNOT 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 02ae795c785dcbc25b56ac513a9237540e57ea63
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849432"
---
# <a name="cnot-operation"></a><span data-ttu-id="906cc-102">CNOT 操作</span><span class="sxs-lookup"><span data-stu-id="906cc-102">CNOT operation</span></span>

<span data-ttu-id="906cc-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="906cc-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="906cc-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="906cc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="906cc-105">制御されていない (CNOT) ゲートを qubits のペアに適用します。</span><span class="sxs-lookup"><span data-stu-id="906cc-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="906cc-106">\begin{align} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & \\ \\ 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}、\end{align} です。</span><span class="sxs-lookup"><span data-stu-id="906cc-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="906cc-107">ここでは、行と列は、クォンタムの概念ガイドのとおりに並べられています。</span><span class="sxs-lookup"><span data-stu-id="906cc-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="906cc-108">入力</span><span class="sxs-lookup"><span data-stu-id="906cc-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="906cc-109">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="906cc-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="906cc-110">CNOT gate の制御 qubit。</span><span class="sxs-lookup"><span data-stu-id="906cc-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="906cc-111">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="906cc-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="906cc-112">CNOT gate のターゲット qubit。</span><span class="sxs-lookup"><span data-stu-id="906cc-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="906cc-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="906cc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="906cc-114">解説</span><span class="sxs-lookup"><span data-stu-id="906cc-114">Remarks</span></span>

<span data-ttu-id="906cc-115">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="906cc-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```