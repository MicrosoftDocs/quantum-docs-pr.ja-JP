---
uid: Microsoft.Quantum.Canon.SwapReverseRegister
title: SwapReverseRegister 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: SwapReverseRegister
qsharp.summary: Uses SWAP gates to Reversed the order of the qubits in a register.
ms.openlocfilehash: 9df62c4ef97a186b274a62bd493fa9e7bbb74fa1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204982"
---
# <a name="swapreverseregister-operation"></a><span data-ttu-id="d72ea-102">SwapReverseRegister 操作</span><span class="sxs-lookup"><span data-stu-id="d72ea-102">SwapReverseRegister operation</span></span>

<span data-ttu-id="d72ea-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d72ea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d72ea-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d72ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d72ea-105">スワップゲートを使用して、レジスタ内の qubits の順序を逆にします。</span><span class="sxs-lookup"><span data-stu-id="d72ea-105">Uses SWAP gates to Reversed the order of the qubits in a register.</span></span>

```qsharp
operation SwapReverseRegister (register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d72ea-106">入力</span><span class="sxs-lookup"><span data-stu-id="d72ea-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="d72ea-107">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d72ea-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d72ea-108">スワップゲートを使用して元に戻す必要がある qubits の順序</span><span class="sxs-lookup"><span data-stu-id="d72ea-108">The qubits order of which should be reversed using SWAP gates</span></span>



## <a name="output--unit"></a><span data-ttu-id="d72ea-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d72ea-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

