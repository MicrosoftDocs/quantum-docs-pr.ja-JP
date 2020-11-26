---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedStatePreparation
title: JWOptimizedStatePreparation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedStatePreparation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: a2e0c24eaa1f5326f2d531b4e7e55b2c440bc795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229853"
---
# <a name="jwoptimizedstatepreparation-operation"></a><span data-ttu-id="249de-102">JWOptimizedStatePreparation 操作</span><span class="sxs-lookup"><span data-stu-id="249de-102">JWOptimizedStatePreparation operation</span></span>

<span data-ttu-id="249de-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="249de-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="249de-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="249de-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="249de-105">スピン orbitals を利用して、評価版の状態を簡単に準備</span><span class="sxs-lookup"><span data-stu-id="249de-105">Simple state preparation of trial state by occupying spin-orbitals</span></span>

```qsharp
operation JWOptimizedStatePreparation (qubitIndices : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="249de-106">入力</span><span class="sxs-lookup"><span data-stu-id="249de-106">Input</span></span>

### <a name="qubitindices--int"></a><span data-ttu-id="249de-107">qubitIndices: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="249de-107">qubitIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="249de-108">原子によって占有される qubits のインデックス。</span><span class="sxs-lookup"><span data-stu-id="249de-108">Indices of qubits to be occupied by electrons.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="249de-109">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="249de-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="249de-110">Hamiltonian の qubits。</span><span class="sxs-lookup"><span data-stu-id="249de-110">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="249de-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="249de-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

