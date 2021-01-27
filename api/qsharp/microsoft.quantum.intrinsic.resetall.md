---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetAll 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 2b8e7fc0e7881d8c1bd6f14c150476262b7a2b19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849315"
---
# <a name="resetall-operation"></a><span data-ttu-id="6ea84-102">ResetAll 操作</span><span class="sxs-lookup"><span data-stu-id="6ea84-102">ResetAll operation</span></span>

<span data-ttu-id="6ea84-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="6ea84-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="6ea84-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="6ea84-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6ea84-105">Qubits の配列を指定した場合は、それらを測定し、安全に解放できるように、それらが | 0 ⟩状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ea84-105">Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.</span></span>

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6ea84-106">入力</span><span class="sxs-lookup"><span data-stu-id="6ea84-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="6ea84-107">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6ea84-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6ea84-108">状態が $ \ket $ にリセットされる qubits の配列 {0} 。</span><span class="sxs-lookup"><span data-stu-id="6ea84-108">An array of qubits whose states are to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ea84-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ea84-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

