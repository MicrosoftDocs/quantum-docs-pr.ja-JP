---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 60ebbdbd1020d41a54426377043fc0c84ceec504
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724553"
---
# <a name="getgeneratorsystemfunction-function"></a><span data-ttu-id="8ced3-102">GetGeneratorSystemFunction 関数</span><span class="sxs-lookup"><span data-stu-id="8ced3-102">GetGeneratorSystemFunction function</span></span>

<span data-ttu-id="8ced3-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8ced3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8ced3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8ced3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8ced3-105">`GeneratorIndex`内の関数を取得 `GeneratorSystem` します。</span><span class="sxs-lookup"><span data-stu-id="8ced3-105">Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.</span></span>

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a><span data-ttu-id="8ced3-106">入力</span><span class="sxs-lookup"><span data-stu-id="8ced3-106">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="8ced3-107">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="8ced3-107">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="8ced3-108">目的の `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="8ced3-108">The `GeneratorSystem` of interest.</span></span>



## <a name="output--int---generatorindex"></a><span data-ttu-id="8ced3-109">出力: [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="8ced3-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="8ced3-110">Hamiltonian 内の各用語にインデックスを付けた関数 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="8ced3-110">An function that indexes each `GeneratorIndex` term in a Hamiltonian.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ced3-111">参照</span><span class="sxs-lookup"><span data-stu-id="8ced3-111">See Also</span></span>

- [<span data-ttu-id="8ced3-112">GeneratorIndex です。</span><span class="sxs-lookup"><span data-stu-id="8ced3-112">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [<span data-ttu-id="8ced3-113">GeneratorSystem です。</span><span class="sxs-lookup"><span data-stu-id="8ced3-113">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)