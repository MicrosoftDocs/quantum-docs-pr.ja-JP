---
uid: Microsoft.Quantum.Intrinsic.SWAP
title: スワップ操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: SWAP
qsharp.summary: >-
  Applies the SWAP gate to a pair of qubits.

  \begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 4d8d037404ac835a1dd032790e7fd03f29591c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849269"
---
# <a name="swap-operation"></a><span data-ttu-id="fbb06-102">スワップ操作</span><span class="sxs-lookup"><span data-stu-id="fbb06-102">SWAP operation</span></span>

<span data-ttu-id="fbb06-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="fbb06-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="fbb06-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="fbb06-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fbb06-105">スワップゲートを qubits のペアに適用します。</span><span class="sxs-lookup"><span data-stu-id="fbb06-105">Applies the SWAP gate to a pair of qubits.</span></span>

<span data-ttu-id="fbb06-106">\begin{align} \ \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 0 \\ \\ & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}、\end{align}</span><span class="sxs-lookup"><span data-stu-id="fbb06-106">\begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="fbb06-107">ここでは、行と列は、クォンタムの概念ガイドのとおりに並べられています。</span><span class="sxs-lookup"><span data-stu-id="fbb06-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation SWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fbb06-108">入力</span><span class="sxs-lookup"><span data-stu-id="fbb06-108">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="fbb06-109">qubit1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fbb06-109">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fbb06-110">交換する最初の qubit。</span><span class="sxs-lookup"><span data-stu-id="fbb06-110">First qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="fbb06-111">qubit2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fbb06-111">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fbb06-112">スワップする2番目の qubit。</span><span class="sxs-lookup"><span data-stu-id="fbb06-112">Second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fbb06-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fbb06-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fbb06-114">解説</span><span class="sxs-lookup"><span data-stu-id="fbb06-114">Remarks</span></span>

<span data-ttu-id="fbb06-115">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="fbb06-115">Equivalent to:</span></span>

```qsharp
CNOT(qubit1, qubit2);
CNOT(qubit2, qubit1);
CNOT(qubit1, qubit2);
```