---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: a902a93968d221349f9a6fa977bbc1706971fcfd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855764"
---
# <a name="interpolategeneratorsystemsimpl-function"></a><span data-ttu-id="e162d-102">InterpolateGeneratorSystemsImpl 関数</span><span class="sxs-lookup"><span data-stu-id="e162d-102">InterpolateGeneratorSystemsImpl function</span></span>

<span data-ttu-id="e162d-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e162d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e162d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e162d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e162d-105">`GeneratorSystems`0 から1までのスケジュールパラメーターに従って、2つの間を直線的に補間 `s` します。</span><span class="sxs-lookup"><span data-stu-id="e162d-105">Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).</span></span>

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="e162d-106">入力</span><span class="sxs-lookup"><span data-stu-id="e162d-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="e162d-107">schedule: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e162d-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e162d-108">スケジュールパラメーター $s \ [0, 1] $。</span><span class="sxs-lookup"><span data-stu-id="e162d-108">A schedule parameter $s\in[0,1]$.</span></span>


### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="e162d-109">generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e162d-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e162d-110">開始 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="e162d-110">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="e162d-111">generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e162d-111">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e162d-112">最後 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="e162d-112">The end `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="e162d-113">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e162d-113">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e162d-114">`GeneratorSystem`入力ジェネレーターシステムの合計であり、weight $ (1-s) $ on `generatorSystemStart` および weight $s $ on のシステムを表す `generatorSystemEnd` 。</span><span class="sxs-lookup"><span data-stu-id="e162d-114">A `GeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e162d-115">参照</span><span class="sxs-lookup"><span data-stu-id="e162d-115">See Also</span></span>

- [<span data-ttu-id="e162d-116">GeneratorSystem です。</span><span class="sxs-lookup"><span data-stu-id="e162d-116">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)