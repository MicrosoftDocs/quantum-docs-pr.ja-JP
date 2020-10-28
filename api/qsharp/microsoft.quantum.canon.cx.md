---
uid: Microsoft.Quantum.Canon.CX
title: CX 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: c430525b71ad4ef0812d90a8ff20c41a5d5b8708
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716373"
---
# <a name="cx-operation"></a><span data-ttu-id="3c324-102">CX 操作</span><span class="sxs-lookup"><span data-stu-id="3c324-102">CX operation</span></span>

<span data-ttu-id="3c324-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c324-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c324-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c324-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c324-105">制御された X (CX) ゲートを qubits のペアに適用します。</span><span class="sxs-lookup"><span data-stu-id="3c324-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="3c324-106">$ $ \begin{align} \ left (\begin{matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 0 & 0 & \\ \\ 1 & 0 \end{matrix}\right) \end{align}、$ $。ここでは、行と列がクォンタムの概念ガイドに従って編成されています。</span><span class="sxs-lookup"><span data-stu-id="3c324-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="3c324-107">入力</span><span class="sxs-lookup"><span data-stu-id="3c324-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="3c324-108">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3c324-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3c324-109">CX ゲートの制御 qubit。</span><span class="sxs-lookup"><span data-stu-id="3c324-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3c324-110">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3c324-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3c324-111">CX ゲートのターゲット qubit。</span><span class="sxs-lookup"><span data-stu-id="3c324-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c324-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c324-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3c324-113">解説</span><span class="sxs-lookup"><span data-stu-id="3c324-113">Remarks</span></span>

<span data-ttu-id="3c324-114">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="3c324-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="3c324-115">および:</span><span class="sxs-lookup"><span data-stu-id="3c324-115">and to:</span></span>

```qsharp
CNOT(control, target);
```