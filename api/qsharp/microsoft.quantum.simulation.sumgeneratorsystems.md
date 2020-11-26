---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: 7cb18e161dce3a52d7c9a0bf6a45d4818db2b849
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192470"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="fa3de-102">SumGeneratorSystems 関数</span><span class="sxs-lookup"><span data-stu-id="fa3de-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="fa3de-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="fa3de-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="fa3de-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa3de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa3de-105">`GeneratorSystem`新しい GeneratorSystem を作成するために、複数のを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa3de-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="fa3de-106">入力</span><span class="sxs-lookup"><span data-stu-id="fa3de-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="fa3de-107">generatorSystems: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="fa3de-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="fa3de-108">`GeneratorSystem[]` 型の配列。</span><span class="sxs-lookup"><span data-stu-id="fa3de-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="fa3de-109">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="fa3de-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="fa3de-110">`GeneratorSystem`入力ジェネレーターシステムの合計であるシステムを表す。</span><span class="sxs-lookup"><span data-stu-id="fa3de-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa3de-111">参照</span><span class="sxs-lookup"><span data-stu-id="fa3de-111">See Also</span></span>

- [<span data-ttu-id="fa3de-112">GeneratorSystem です。</span><span class="sxs-lookup"><span data-stu-id="fa3de-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)