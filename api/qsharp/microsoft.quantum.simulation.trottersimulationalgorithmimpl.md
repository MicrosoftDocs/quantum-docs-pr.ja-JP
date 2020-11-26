---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: TrotterSimulationAlgorithmImpl 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 5b796245e2a4434228260a229cb61be66f3e38d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203401"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="ec5ba-102">TrotterSimulationAlgorithmImpl 操作</span><span class="sxs-lookup"><span data-stu-id="ec5ba-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="ec5ba-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ec5ba-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ec5ba-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec5ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec5ba-105">に対してを繰り返し呼び出し `TrotterStep` 、時間の進化演算子 exp (_-iht_) を概算します。</span><span class="sxs-lookup"><span data-stu-id="ec5ba-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ec5ba-106">入力</span><span class="sxs-lookup"><span data-stu-id="ec5ba-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="ec5ba-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ec5ba-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ec5ba-108">単一の Trotter ステップでシミュレートされた時間の進化の期間。</span><span class="sxs-lookup"><span data-stu-id="ec5ba-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="ec5ba-109">trotterOrder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ec5ba-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ec5ba-110">Trotter インテグレーターの順序。</span><span class="sxs-lookup"><span data-stu-id="ec5ba-110">Order of Trotter integrator.</span></span> <span data-ttu-id="ec5ba-111">この値には、1または偶数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec5ba-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="ec5ba-112">maxTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ec5ba-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ec5ba-113">シミュレーションの合計期間 $t $。</span><span class="sxs-lookup"><span data-stu-id="ec5ba-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="ec5ba-114">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="ec5ba-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="ec5ba-115">シミュレートするシステムの完全な説明。</span><span class="sxs-lookup"><span data-stu-id="ec5ba-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ec5ba-116">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ec5ba-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ec5ba-117">シミュレーションによって処理された qubits。</span><span class="sxs-lookup"><span data-stu-id="ec5ba-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ec5ba-118">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec5ba-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

