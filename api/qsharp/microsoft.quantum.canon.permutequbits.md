---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 0f4d8819d5b08f4d5370f8fdc407b2eb2a3e5f21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715659"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="23432-102">PermuteQubits 操作</span><span class="sxs-lookup"><span data-stu-id="23432-102">PermuteQubits operation</span></span>

<span data-ttu-id="23432-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="23432-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="23432-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="23432-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="23432-105">スワップ操作を使用した Permutes qubits。</span><span class="sxs-lookup"><span data-stu-id="23432-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="23432-106">入力</span><span class="sxs-lookup"><span data-stu-id="23432-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="23432-107">順序付け: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="23432-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="23432-108">Qubits の新しい順序について説明します。ここで、インデックス i の qubits は [i] の順に並べられます。</span><span class="sxs-lookup"><span data-stu-id="23432-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="23432-109">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="23432-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="23432-110">操作する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="23432-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="23432-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="23432-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
