---
uid: Microsoft.Quantum.Canon.CY
title: CY 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4a1a533421dd9205e973d5e8237d67b20bc4886d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216576"
---
# <a name="cy-operation"></a><span data-ttu-id="a08ef-102">CY 操作</span><span class="sxs-lookup"><span data-stu-id="a08ef-102">CY operation</span></span>

<span data-ttu-id="a08ef-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a08ef-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a08ef-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a08ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a08ef-105">コントロール-Y (CY) ゲートを qubits のペアに適用します。</span><span class="sxs-lookup"><span data-stu-id="a08ef-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="a08ef-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & 0 & \\ \\ -i 0 & 0 \\ \\ & i & 0 \end{align}、$ $。ここでは、行と列がクォンタムの概念ガイドに従って編成されています。</span><span class="sxs-lookup"><span data-stu-id="a08ef-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a08ef-107">入力</span><span class="sxs-lookup"><span data-stu-id="a08ef-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="a08ef-108">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a08ef-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a08ef-109">CY ゲートの制御 qubit。</span><span class="sxs-lookup"><span data-stu-id="a08ef-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a08ef-110">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a08ef-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a08ef-111">CY ゲートのターゲット qubit。</span><span class="sxs-lookup"><span data-stu-id="a08ef-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a08ef-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a08ef-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a08ef-113">解説</span><span class="sxs-lookup"><span data-stu-id="a08ef-113">Remarks</span></span>

<span data-ttu-id="a08ef-114">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="a08ef-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```