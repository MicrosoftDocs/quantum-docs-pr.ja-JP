---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetAll 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 00b7c0f508d76fb0f5b46c7ec00c0718469365a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711412"
---
# <a name="resetall-operation"></a><span data-ttu-id="8479f-102">ResetAll 操作</span><span class="sxs-lookup"><span data-stu-id="8479f-102">ResetAll operation</span></span>

<span data-ttu-id="8479f-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="8479f-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="8479f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8479f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8479f-105">Qubits の配列を指定した場合は、それらを測定し、安全に解放できるように、それらが | 0 ⟩状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8479f-105">Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.</span></span>

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8479f-106">入力</span><span class="sxs-lookup"><span data-stu-id="8479f-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="8479f-107">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8479f-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8479f-108">状態が $ \ket $ にリセットされる qubits の配列 {0} 。</span><span class="sxs-lookup"><span data-stu-id="8479f-108">An array of qubits whose states are to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8479f-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8479f-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

