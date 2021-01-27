---
uid: Microsoft.Quantum.Canon.CY
title: CY 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 862f058e630ee6d9159e0fe514ca2dd1179ea9a2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840736"
---
# <a name="cy-operation"></a><span data-ttu-id="f734f-102">CY 操作</span><span class="sxs-lookup"><span data-stu-id="f734f-102">CY operation</span></span>

<span data-ttu-id="f734f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f734f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f734f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f734f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f734f-105">コントロール-Y (CY) ゲートを qubits のペアに適用します。</span><span class="sxs-lookup"><span data-stu-id="f734f-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="f734f-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & 0 & \\ \\ -i 0 & 0 \\ \\ & i & 0 \end{align}、$ $。ここでは、行と列がクォンタムの概念ガイドに従って編成されています。</span><span class="sxs-lookup"><span data-stu-id="f734f-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f734f-107">入力</span><span class="sxs-lookup"><span data-stu-id="f734f-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="f734f-108">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f734f-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f734f-109">CY ゲートの制御 qubit。</span><span class="sxs-lookup"><span data-stu-id="f734f-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f734f-110">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f734f-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f734f-111">CY ゲートのターゲット qubit。</span><span class="sxs-lookup"><span data-stu-id="f734f-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f734f-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f734f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f734f-113">解説</span><span class="sxs-lookup"><span data-stu-id="f734f-113">Remarks</span></span>

<span data-ttu-id="f734f-114">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="f734f-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```