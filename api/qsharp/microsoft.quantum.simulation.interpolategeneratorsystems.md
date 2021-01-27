---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: InterpolateGeneratorSystems 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: c56f1eaf13afb649777c0d9368e97d85996cc67b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842258"
---
# <a name="interpolategeneratorsystems-function"></a><span data-ttu-id="9dd65-102">InterpolateGeneratorSystems 関数</span><span class="sxs-lookup"><span data-stu-id="9dd65-102">InterpolateGeneratorSystems function</span></span>

<span data-ttu-id="9dd65-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9dd65-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9dd65-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9dd65-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9dd65-105">`TimeDependentGeneratorSystem`2 つのの間の線形補間を表すを返し `GeneratorSystem` ます。</span><span class="sxs-lookup"><span data-stu-id="9dd65-105">Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.</span></span>

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="9dd65-106">入力</span><span class="sxs-lookup"><span data-stu-id="9dd65-106">Input</span></span>

### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="9dd65-107">generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="9dd65-107">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="9dd65-108">開始 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="9dd65-108">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="9dd65-109">generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="9dd65-109">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="9dd65-110">最後 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="9dd65-110">The end `GeneratorSystem`.</span></span>



## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="9dd65-111">出力: [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="9dd65-111">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="9dd65-112">`TimeDependentGeneratorSystem`入力ジェネレーターシステムの合計であり、weight $ (1-s) $ on `generatorSystemStart` および weight $s $ on のシステムを表す `generatorSystemEnd` 。</span><span class="sxs-lookup"><span data-stu-id="9dd65-112">A `TimeDependentGeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="9dd65-113">参照</span><span class="sxs-lookup"><span data-stu-id="9dd65-113">See Also</span></span>

- [<span data-ttu-id="9dd65-114">GeneratorSystem です。</span><span class="sxs-lookup"><span data-stu-id="9dd65-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [<span data-ttu-id="9dd65-115">TimeDependentGeneratorSystem です。</span><span class="sxs-lookup"><span data-stu-id="9dd65-115">Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)