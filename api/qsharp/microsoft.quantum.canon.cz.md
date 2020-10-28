---
uid: Microsoft.Quantum.Canon.CZ
title: CS-CZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: bc38cd43a0dcaf7aea735ef6468a394e91c85593
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716345"
---
# <a name="cz-operation"></a><span data-ttu-id="c15fd-102">CS-CZ 操作</span><span class="sxs-lookup"><span data-stu-id="c15fd-102">CZ operation</span></span>

<span data-ttu-id="c15fd-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c15fd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c15fd-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c15fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c15fd-105">CS-CZ ゲートを qubits のペアに適用します。</span><span class="sxs-lookup"><span data-stu-id="c15fd-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="c15fd-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 \\ \\ & 0 & 1 & 0 0 & \\ \\ 0 & 0 &-1 \end{align}、$ $。ここでは、行と列がクォンタムの概念ガイドに従って編成されています。</span><span class="sxs-lookup"><span data-stu-id="c15fd-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="c15fd-107">入力</span><span class="sxs-lookup"><span data-stu-id="c15fd-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="c15fd-108">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c15fd-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c15fd-109">CS-CZ gate の制御 qubit。</span><span class="sxs-lookup"><span data-stu-id="c15fd-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c15fd-110">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c15fd-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c15fd-111">CS-CZ gate のターゲット qubit。</span><span class="sxs-lookup"><span data-stu-id="c15fd-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c15fd-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c15fd-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c15fd-113">解説</span><span class="sxs-lookup"><span data-stu-id="c15fd-113">Remarks</span></span>

<span data-ttu-id="c15fd-114">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="c15fd-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```