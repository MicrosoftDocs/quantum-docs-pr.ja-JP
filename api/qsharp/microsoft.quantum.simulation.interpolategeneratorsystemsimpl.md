---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 212ed4c473fab3572f73ea250061057ad13e393f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709438"
---
# <a name="interpolategeneratorsystemsimpl-function"></a><span data-ttu-id="c70fa-102">InterpolateGeneratorSystemsImpl 関数</span><span class="sxs-lookup"><span data-stu-id="c70fa-102">InterpolateGeneratorSystemsImpl function</span></span>

<span data-ttu-id="c70fa-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c70fa-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c70fa-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c70fa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c70fa-105">`GeneratorSystems`0 から1までのスケジュールパラメーターに従って、2つの間を直線的に補間 `s` します。</span><span class="sxs-lookup"><span data-stu-id="c70fa-105">Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).</span></span>

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="c70fa-106">入力</span><span class="sxs-lookup"><span data-stu-id="c70fa-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="c70fa-107">schedule: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c70fa-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c70fa-108">スケジュールパラメーター $s \ [0, 1] $。</span><span class="sxs-lookup"><span data-stu-id="c70fa-108">A schedule parameter $s\in[0,1]$.</span></span>


### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="c70fa-109">generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="c70fa-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="c70fa-110">開始 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="c70fa-110">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="c70fa-111">generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="c70fa-111">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="c70fa-112">最後 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="c70fa-112">The end `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="c70fa-113">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="c70fa-113">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="c70fa-114">`GeneratorSystem`入力ジェネレーターシステムの合計であり、weight $ (1-s) $ on `generatorSystemStart` および weight $s $ on のシステムを表す `generatorSystemEnd` 。</span><span class="sxs-lookup"><span data-stu-id="c70fa-114">A `GeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c70fa-115">参照</span><span class="sxs-lookup"><span data-stu-id="c70fa-115">See Also</span></span>

- [<span data-ttu-id="c70fa-116">GeneratorSystem です。</span><span class="sxs-lookup"><span data-stu-id="c70fa-116">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)