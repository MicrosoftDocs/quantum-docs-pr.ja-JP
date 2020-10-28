---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725351"
---
# <a name="trotterstep-function"></a><span data-ttu-id="34a7e-102">TrotterStep 関数</span><span class="sxs-lookup"><span data-stu-id="34a7e-102">TrotterStep function</span></span>

<span data-ttu-id="34a7e-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="34a7e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="34a7e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="34a7e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="34a7e-105">Trotter – Suzuki 分解を使用して、「」で説明されているシステムによる時間の短縮の単一の時間ステップを実装 `EvolutionGenerator` します。</span><span class="sxs-lookup"><span data-stu-id="34a7e-105">Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.</span></span>

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="34a7e-106">入力</span><span class="sxs-lookup"><span data-stu-id="34a7e-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="34a7e-107">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="34a7e-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="34a7e-108">シミュレートするシステムの完全な説明。</span><span class="sxs-lookup"><span data-stu-id="34a7e-108">A complete description of the system to be simulated.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="34a7e-109">trotterOrder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="34a7e-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="34a7e-110">Trotter インテグレーターの順序。</span><span class="sxs-lookup"><span data-stu-id="34a7e-110">Order of Trotter integrator.</span></span> <span data-ttu-id="34a7e-111">この値には、1または偶数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34a7e-111">This must be either 1 or an even number.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="34a7e-112">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="34a7e-112">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="34a7e-113">単一の Trotter ステップでシミュレートされた時間の進化の期間。</span><span class="sxs-lookup"><span data-stu-id="34a7e-113">Duration of simulated time-evolution in single Trotter step.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="34a7e-114">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="34a7e-114">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="34a7e-115">時間の短縮の1つのステップに近似する、期間の単一のステップを近似する、ユニタリ操作 `trotterStepSize` 。</span><span class="sxs-lookup"><span data-stu-id="34a7e-115">Unitary operation that approximates a single step of time-evolution for duration `trotterStepSize`.</span></span>

## <a name="remarks"></a><span data-ttu-id="34a7e-116">解説</span><span class="sxs-lookup"><span data-stu-id="34a7e-116">Remarks</span></span>

<span data-ttu-id="34a7e-117">Trotter – Suzuki 分解の詳細については、「 [時間順序の構成](/quantum/libraries/control-flow#time-ordered-composition)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34a7e-117">For more on the Trotter–Suzuki decomposition, see [Time-Ordered Composition](/quantum/libraries/control-flow#time-ordered-composition).</span></span>