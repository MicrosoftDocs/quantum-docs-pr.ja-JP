---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedHpqTerm
title: _JWOptimizedHpqTerm 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedHpqTerm
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: 503de03a379ac0ede3754aa7a31ac2ce84e5c675
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724875"
---
# <a name="_jwoptimizedhpqterm-operation"></a><span data-ttu-id="7db00-102">_JWOptimizedHpqTerm 操作</span><span class="sxs-lookup"><span data-stu-id="7db00-102">_JWOptimizedHpqTerm operation</span></span>

<span data-ttu-id="7db00-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7db00-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="7db00-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7db00-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7db00-105">によって記述された PQ 用語によって時間の進化を適用 `GeneratorIndex` します。</span><span class="sxs-lookup"><span data-stu-id="7db00-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedHpqTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7db00-106">入力</span><span class="sxs-lookup"><span data-stu-id="7db00-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="7db00-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="7db00-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="7db00-108">`GeneratorIndex` PQ 用語を表します。</span><span class="sxs-lookup"><span data-stu-id="7db00-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="7db00-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7db00-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7db00-110">時間の進化の期間。</span><span class="sxs-lookup"><span data-stu-id="7db00-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="7db00-111">parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7db00-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7db00-112">タイム進化の符号を決定する qubit。</span><span class="sxs-lookup"><span data-stu-id="7db00-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="7db00-113">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7db00-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7db00-114">Hamiltonian の qubits。</span><span class="sxs-lookup"><span data-stu-id="7db00-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7db00-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7db00-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

