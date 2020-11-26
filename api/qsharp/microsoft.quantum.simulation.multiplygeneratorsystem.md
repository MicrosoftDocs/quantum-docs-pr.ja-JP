---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: effb9e3ca754f77bbe1ea0fb6ca30ae49e92d531
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229156"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="a341e-102">MultiplyGeneratorSystem 関数</span><span class="sxs-lookup"><span data-stu-id="a341e-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="a341e-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a341e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a341e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a341e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a341e-105">内のすべての用語の係数を乗算し `GeneratorSystem` ます。</span><span class="sxs-lookup"><span data-stu-id="a341e-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="a341e-106">入力</span><span class="sxs-lookup"><span data-stu-id="a341e-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="a341e-107">乗数: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a341e-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a341e-108">係数の乗数。</span><span class="sxs-lookup"><span data-stu-id="a341e-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="a341e-109">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a341e-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a341e-110">乗算する `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="a341e-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="a341e-111">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a341e-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a341e-112">係数の係数 `GeneratorSystem` が大きいシステムを表す `multiplier` 。</span><span class="sxs-lookup"><span data-stu-id="a341e-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="a341e-113">参照</span><span class="sxs-lookup"><span data-stu-id="a341e-113">See Also</span></span>

- [<span data-ttu-id="a341e-114">GeneratorSystem です。</span><span class="sxs-lookup"><span data-stu-id="a341e-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)