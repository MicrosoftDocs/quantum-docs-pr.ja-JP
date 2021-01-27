---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSingleConfigurationalStateSingleSiteOccupation
title: PrepareSingleConfigurationalStateSingleSiteOccupation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSingleConfigurationalStateSingleSiteOccupation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: db268c92fd778d61f324128947b5e5b78c2a5b4e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98836509"
---
# <a name="preparesingleconfigurationalstatesinglesiteoccupation-operation"></a><span data-ttu-id="6858b-102">PrepareSingleConfigurationalStateSingleSiteOccupation 操作</span><span class="sxs-lookup"><span data-stu-id="6858b-102">PrepareSingleConfigurationalStateSingleSiteOccupation operation</span></span>

<span data-ttu-id="6858b-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="6858b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="6858b-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6858b-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="6858b-105">スピン orbitals を利用して、評価版の状態を簡単に準備</span><span class="sxs-lookup"><span data-stu-id="6858b-105">Simple state preparation of trial state by occupying spin-orbitals</span></span>

```qsharp
operation PrepareSingleConfigurationalStateSingleSiteOccupation (qubitIndices : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6858b-106">入力</span><span class="sxs-lookup"><span data-stu-id="6858b-106">Input</span></span>

### <a name="qubitindices--int"></a><span data-ttu-id="6858b-107">qubitIndices: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6858b-107">qubitIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6858b-108">原子によって占有される qubits のインデックス。</span><span class="sxs-lookup"><span data-stu-id="6858b-108">Indices of qubits to be occupied by electrons.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="6858b-109">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6858b-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6858b-110">Hamiltonian の qubits。</span><span class="sxs-lookup"><span data-stu-id="6858b-110">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6858b-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6858b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

