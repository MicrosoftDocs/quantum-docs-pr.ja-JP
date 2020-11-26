---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: deb5fa5b0bc0509c957e01bf22e491ad3e2214f3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205607"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="72475-102">PermuteQubits 操作</span><span class="sxs-lookup"><span data-stu-id="72475-102">PermuteQubits operation</span></span>

<span data-ttu-id="72475-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="72475-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="72475-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72475-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72475-105">スワップ操作を使用した Permutes qubits。</span><span class="sxs-lookup"><span data-stu-id="72475-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="72475-106">入力</span><span class="sxs-lookup"><span data-stu-id="72475-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="72475-107">順序付け: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="72475-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="72475-108">Qubits の新しい順序について説明します。ここで、インデックス i の qubits は [i] の順に並べられます。</span><span class="sxs-lookup"><span data-stu-id="72475-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="72475-109">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="72475-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="72475-110">操作する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="72475-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72475-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72475-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

