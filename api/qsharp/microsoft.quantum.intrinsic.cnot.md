---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNOT 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 2fb5b4df189fb3ab23b2ca5cb273b2451ffcc067
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722672"
---
# <a name="cnot-operation"></a><span data-ttu-id="ff89e-102">CNOT 操作</span><span class="sxs-lookup"><span data-stu-id="ff89e-102">CNOT operation</span></span>

<span data-ttu-id="ff89e-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ff89e-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ff89e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff89e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff89e-105">制御されていない (CNOT) ゲートを qubits のペアに適用します。</span><span class="sxs-lookup"><span data-stu-id="ff89e-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="ff89e-106">\begin{align} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & \\ \\ 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}、\end{align} です。</span><span class="sxs-lookup"><span data-stu-id="ff89e-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="ff89e-107">ここでは、行と列は、クォンタムの概念ガイドのとおりに並べられています。</span><span class="sxs-lookup"><span data-stu-id="ff89e-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ff89e-108">入力</span><span class="sxs-lookup"><span data-stu-id="ff89e-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="ff89e-109">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ff89e-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ff89e-110">CNOT gate の制御 qubit。</span><span class="sxs-lookup"><span data-stu-id="ff89e-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ff89e-111">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ff89e-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ff89e-112">CNOT gate のターゲット qubit。</span><span class="sxs-lookup"><span data-stu-id="ff89e-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff89e-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff89e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ff89e-114">解説</span><span class="sxs-lookup"><span data-stu-id="ff89e-114">Remarks</span></span>

<span data-ttu-id="ff89e-115">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="ff89e-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```