---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719863"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="83560-102">TrotterSimulationAlgorithm 関数</span><span class="sxs-lookup"><span data-stu-id="83560-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="83560-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="83560-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="83560-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="83560-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="83560-105">`SimulationAlgorithm` Trotter – Suzuki 分解を使用して、時間の進化演算子 _exp (-iHt)_ を概算する関数。</span><span class="sxs-lookup"><span data-stu-id="83560-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_ .</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="83560-106">入力</span><span class="sxs-lookup"><span data-stu-id="83560-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="83560-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="83560-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="83560-108">単一の Trotter ステップでシミュレートされた時間の進化の期間。</span><span class="sxs-lookup"><span data-stu-id="83560-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="83560-109">trotterOrder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="83560-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="83560-110">Trotter インテグレーターの順序。</span><span class="sxs-lookup"><span data-stu-id="83560-110">Order of Trotter integrator.</span></span> <span data-ttu-id="83560-111">この値には、1または偶数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83560-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="83560-112">出力: [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="83560-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="83560-113">`SimulationAlgorithm` 型。</span><span class="sxs-lookup"><span data-stu-id="83560-113">A `SimulationAlgorithm` type.</span></span>