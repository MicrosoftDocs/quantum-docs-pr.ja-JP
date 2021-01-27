---
uid: Microsoft.Quantum.Canon.CZ
title: CS-CZ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: cef1544fb76d561cfd0949c84c487550d523bb85
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840702"
---
# <a name="cz-operation"></a><span data-ttu-id="8e919-102">CS-CZ 操作</span><span class="sxs-lookup"><span data-stu-id="8e919-102">CZ operation</span></span>

<span data-ttu-id="8e919-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8e919-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8e919-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8e919-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8e919-105">CS-CZ ゲートを qubits のペアに適用します。</span><span class="sxs-lookup"><span data-stu-id="8e919-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="8e919-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 \\ \\ & 0 & 1 & 0 0 & \\ \\ 0 & 0 &-1 \end{align}、$ $。ここでは、行と列がクォンタムの概念ガイドに従って編成されています。</span><span class="sxs-lookup"><span data-stu-id="8e919-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8e919-107">入力</span><span class="sxs-lookup"><span data-stu-id="8e919-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="8e919-108">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8e919-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8e919-109">CS-CZ gate の制御 qubit。</span><span class="sxs-lookup"><span data-stu-id="8e919-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8e919-110">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8e919-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8e919-111">CS-CZ gate のターゲット qubit。</span><span class="sxs-lookup"><span data-stu-id="8e919-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8e919-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e919-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8e919-113">解説</span><span class="sxs-lookup"><span data-stu-id="8e919-113">Remarks</span></span>

<span data-ttu-id="8e919-114">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="8e919-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```