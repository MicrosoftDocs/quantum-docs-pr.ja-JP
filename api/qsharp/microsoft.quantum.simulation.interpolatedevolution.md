---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: InterpolatedEvolution 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 18026b9872f6a3344a1e5c2122f55927975ccb59
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710586"
---
# <a name="interpolatedevolution-function"></a><span data-ttu-id="b093e-102">InterpolatedEvolution 関数</span><span class="sxs-lookup"><span data-stu-id="b093e-102">InterpolatedEvolution function</span></span>

<span data-ttu-id="b093e-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b093e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b093e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b093e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b093e-105">一定のスケジュールで2つのジェネレーターの間を補間し、結果として得られる時間に依存するジェネレーターの下で、シミュレートされた進化を qubit レジスタに適用する操作を返します。</span><span class="sxs-lookup"><span data-stu-id="b093e-105">Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.</span></span>

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="b093e-106">入力</span><span class="sxs-lookup"><span data-stu-id="b093e-106">Input</span></span>

### <a name="interpolationtime--double"></a><span data-ttu-id="b093e-107">interpolationTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b093e-107">interpolationTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b093e-108">補間を実行する時間。</span><span class="sxs-lookup"><span data-stu-id="b093e-108">Time to perform the interpolation over.</span></span>


### <a name="evolutiongeneratorstart--evolutiongenerator"></a><span data-ttu-id="b093e-109">evolutionGeneratorStart: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="b093e-109">evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="b093e-110">下の進化をシミュレートするための初期ジェネレーター。</span><span class="sxs-lookup"><span data-stu-id="b093e-110">Initial generator to simulate evolution under.</span></span>


### <a name="evolutiongeneratorend--evolutiongenerator"></a><span data-ttu-id="b093e-111">evolutionGeneratorEnd: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="b093e-111">evolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="b093e-112">下の進化をシミュレートする最終的なジェネレーター。</span><span class="sxs-lookup"><span data-stu-id="b093e-112">Final generator to simulate evolution under.</span></span>


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a><span data-ttu-id="b093e-113">timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="b093e-113">timeDependentSimulationAlgorithm : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="b093e-114">時間に依存するシミュレーションアルゴリズム。これは、一様補間のスケジュールでの進化をシミュレートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b093e-114">A time-dependent simulation algorithm that will be used to simulate evolution during the uniform interpolation schedule.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="b093e-115">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="b093e-115">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="b093e-116">解説</span><span class="sxs-lookup"><span data-stu-id="b093e-116">Remarks</span></span>

<span data-ttu-id="b093e-117">Adiabatic 条件を満たすために補間時間を選択した場合、この関数は、最終的な dynamical ジェネレーターの adiabatic 状態の準備を実行する操作を返します。</span><span class="sxs-lookup"><span data-stu-id="b093e-117">If the interpolation time is chosen to meet the adiabatic conditions, then this function returns an operation which performs adiabatic state preparation for the final dynamical generator.</span></span>