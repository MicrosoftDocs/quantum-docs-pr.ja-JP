---
uid: Microsoft.Quantum.Canon.CZ
title: CS-CZ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 419082dbf8f96a9fe2dfabeab77e1823cb59a8f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207209"
---
# <a name="cz-operation"></a><span data-ttu-id="72c31-102">CS-CZ 操作</span><span class="sxs-lookup"><span data-stu-id="72c31-102">CZ operation</span></span>

<span data-ttu-id="72c31-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="72c31-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="72c31-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72c31-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72c31-105">CS-CZ ゲートを qubits のペアに適用します。</span><span class="sxs-lookup"><span data-stu-id="72c31-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="72c31-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 \\ \\ & 0 & 1 & 0 0 & \\ \\ 0 & 0 &-1 \end{align}、$ $。ここでは、行と列がクォンタムの概念ガイドに従って編成されています。</span><span class="sxs-lookup"><span data-stu-id="72c31-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="72c31-107">入力</span><span class="sxs-lookup"><span data-stu-id="72c31-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="72c31-108">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="72c31-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="72c31-109">CS-CZ gate の制御 qubit。</span><span class="sxs-lookup"><span data-stu-id="72c31-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="72c31-110">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="72c31-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="72c31-111">CS-CZ gate のターゲット qubit。</span><span class="sxs-lookup"><span data-stu-id="72c31-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72c31-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72c31-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="72c31-113">解説</span><span class="sxs-lookup"><span data-stu-id="72c31-113">Remarks</span></span>

<span data-ttu-id="72c31-114">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="72c31-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```