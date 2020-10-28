---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: b667a6af313b5bb8950a34a6d0406976bde49311
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719882"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="ff88b-102">SumGeneratorSystems 関数</span><span class="sxs-lookup"><span data-stu-id="ff88b-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="ff88b-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ff88b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ff88b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff88b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff88b-105">`GeneratorSystem`新しい GeneratorSystem を作成するために、複数のを追加します。</span><span class="sxs-lookup"><span data-stu-id="ff88b-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="ff88b-106">入力</span><span class="sxs-lookup"><span data-stu-id="ff88b-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="ff88b-107">generatorSystems: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="ff88b-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="ff88b-108">`GeneratorSystem[]` 型の配列。</span><span class="sxs-lookup"><span data-stu-id="ff88b-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="ff88b-109">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="ff88b-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="ff88b-110">`GeneratorSystem`入力ジェネレーターシステムの合計であるシステムを表す。</span><span class="sxs-lookup"><span data-stu-id="ff88b-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff88b-111">参照</span><span class="sxs-lookup"><span data-stu-id="ff88b-111">See Also</span></span>

- [<span data-ttu-id="ff88b-112">GeneratorSystem です。</span><span class="sxs-lookup"><span data-stu-id="ff88b-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)