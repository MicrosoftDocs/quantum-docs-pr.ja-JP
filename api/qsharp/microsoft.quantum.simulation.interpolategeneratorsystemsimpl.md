---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 1ca9580ba603db8fee40e008a7ea51cb7a04d7d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229224"
---
# <a name="interpolategeneratorsystemsimpl-function"></a><span data-ttu-id="a69af-102">InterpolateGeneratorSystemsImpl 関数</span><span class="sxs-lookup"><span data-stu-id="a69af-102">InterpolateGeneratorSystemsImpl function</span></span>

<span data-ttu-id="a69af-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a69af-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a69af-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a69af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a69af-105">`GeneratorSystems`0 から1までのスケジュールパラメーターに従って、2つの間を直線的に補間 `s` します。</span><span class="sxs-lookup"><span data-stu-id="a69af-105">Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).</span></span>

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="a69af-106">入力</span><span class="sxs-lookup"><span data-stu-id="a69af-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="a69af-107">schedule: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a69af-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a69af-108">スケジュールパラメーター $s \ [0, 1] $。</span><span class="sxs-lookup"><span data-stu-id="a69af-108">A schedule parameter $s\in[0,1]$.</span></span>


### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="a69af-109">generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a69af-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a69af-110">開始 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="a69af-110">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="a69af-111">generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a69af-111">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a69af-112">最後 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="a69af-112">The end `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="a69af-113">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a69af-113">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a69af-114">`GeneratorSystem`入力ジェネレーターシステムの合計であり、weight $ (1-s) $ on `generatorSystemStart` および weight $s $ on のシステムを表す `generatorSystemEnd` 。</span><span class="sxs-lookup"><span data-stu-id="a69af-114">A `GeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a69af-115">参照</span><span class="sxs-lookup"><span data-stu-id="a69af-115">See Also</span></span>

- [<span data-ttu-id="a69af-116">GeneratorSystem です。</span><span class="sxs-lookup"><span data-stu-id="a69af-116">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)