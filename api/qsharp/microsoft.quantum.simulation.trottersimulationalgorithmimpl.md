---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: TrotterSimulationAlgorithmImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 2af68532d700a1fb5b037707ce4650696cbe1a64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725360"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="0e36b-102">TrotterSimulationAlgorithmImpl 操作</span><span class="sxs-lookup"><span data-stu-id="0e36b-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="0e36b-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0e36b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0e36b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e36b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e36b-105">に対してを繰り返し呼び出し `TrotterStep` 、時間の進化演算子 exp ( _-iht_ ) を概算します。</span><span class="sxs-lookup"><span data-stu-id="0e36b-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp( _-iHt_ ).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0e36b-106">入力</span><span class="sxs-lookup"><span data-stu-id="0e36b-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="0e36b-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0e36b-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0e36b-108">単一の Trotter ステップでシミュレートされた時間の進化の期間。</span><span class="sxs-lookup"><span data-stu-id="0e36b-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="0e36b-109">trotterOrder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0e36b-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0e36b-110">Trotter インテグレーターの順序。</span><span class="sxs-lookup"><span data-stu-id="0e36b-110">Order of Trotter integrator.</span></span> <span data-ttu-id="0e36b-111">この値には、1または偶数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e36b-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="0e36b-112">maxTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0e36b-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0e36b-113">シミュレーションの合計期間 $t $。</span><span class="sxs-lookup"><span data-stu-id="0e36b-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="0e36b-114">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="0e36b-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="0e36b-115">シミュレートするシステムの完全な説明。</span><span class="sxs-lookup"><span data-stu-id="0e36b-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="0e36b-116">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0e36b-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0e36b-117">シミュレーションによって処理された qubits。</span><span class="sxs-lookup"><span data-stu-id="0e36b-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e36b-118">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e36b-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

