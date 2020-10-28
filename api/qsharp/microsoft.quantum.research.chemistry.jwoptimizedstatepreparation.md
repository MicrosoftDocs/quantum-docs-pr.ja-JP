---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedStatePreparation
title: JWOptimizedStatePreparation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedStatePreparation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: 70154eeb5477c474acbb47d7f6417e42b515371e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710773"
---
# <a name="jwoptimizedstatepreparation-operation"></a><span data-ttu-id="31761-102">JWOptimizedStatePreparation 操作</span><span class="sxs-lookup"><span data-stu-id="31761-102">JWOptimizedStatePreparation operation</span></span>

<span data-ttu-id="31761-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="31761-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="31761-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31761-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31761-105">スピン orbitals を利用して、評価版の状態を簡単に準備</span><span class="sxs-lookup"><span data-stu-id="31761-105">Simple state preparation of trial state by occupying spin-orbitals</span></span>

```qsharp
operation JWOptimizedStatePreparation (qubitIndices : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="31761-106">入力</span><span class="sxs-lookup"><span data-stu-id="31761-106">Input</span></span>

### <a name="qubitindices--int"></a><span data-ttu-id="31761-107">qubitIndices: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="31761-107">qubitIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="31761-108">原子によって占有される qubits のインデックス。</span><span class="sxs-lookup"><span data-stu-id="31761-108">Indices of qubits to be occupied by electrons.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="31761-109">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="31761-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="31761-110">Hamiltonian の qubits。</span><span class="sxs-lookup"><span data-stu-id="31761-110">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="31761-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="31761-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

