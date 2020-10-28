---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: TimeDependentTrotterSimulationAlgorithmImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: c6d1c976d29c69d3ac14d9a2be09826602c8cc1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719858"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a><span data-ttu-id="fa434-102">TimeDependentTrotterSimulationAlgorithmImpl 操作</span><span class="sxs-lookup"><span data-stu-id="fa434-102">TimeDependentTrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="fa434-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="fa434-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="fa434-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fa434-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fa434-105">時間に依存する Schrödinger 式を解決するための、複数の Trotter ステップの実装。</span><span class="sxs-lookup"><span data-stu-id="fa434-105">Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.</span></span>

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="fa434-106">入力</span><span class="sxs-lookup"><span data-stu-id="fa434-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="fa434-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fa434-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fa434-108">単一の Trotter ステップでシミュレートされた時間の進化の期間。</span><span class="sxs-lookup"><span data-stu-id="fa434-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="fa434-109">trotterOrder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fa434-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fa434-110">Trotter インテグレーターの順序。</span><span class="sxs-lookup"><span data-stu-id="fa434-110">Order of Trotter integrator.</span></span> <span data-ttu-id="fa434-111">この値には、1または偶数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa434-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="fa434-112">maxTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fa434-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fa434-113">シミュレーションの合計期間 $t $。</span><span class="sxs-lookup"><span data-stu-id="fa434-113">Total duration of simulation $t$.</span></span>


### <a name="evolutionschedule--evolutionschedule"></a><span data-ttu-id="fa434-114">evolutionSchedule: [evolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span><span class="sxs-lookup"><span data-stu-id="fa434-114">evolutionSchedule : [EvolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span></span>

<span data-ttu-id="fa434-115">シミュレートする時間に依存するシステムの完全な説明。</span><span class="sxs-lookup"><span data-stu-id="fa434-115">A complete description of the time-dependent system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="fa434-116">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fa434-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fa434-117">シミュレーションによって処理された qubits。</span><span class="sxs-lookup"><span data-stu-id="fa434-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fa434-118">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fa434-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

