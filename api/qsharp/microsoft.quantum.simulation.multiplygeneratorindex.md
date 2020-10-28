---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: 9ee0568073b65b027cc98eb56934e9286b59c27f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724492"
---
# <a name="multiplygeneratorindex-function"></a><span data-ttu-id="f5b8e-102">MultiplyGeneratorIndex 関数</span><span class="sxs-lookup"><span data-stu-id="f5b8e-102">MultiplyGeneratorIndex function</span></span>

<span data-ttu-id="f5b8e-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f5b8e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f5b8e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f5b8e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f5b8e-105">内の係数を乗算 `GeneratorIndex` します。</span><span class="sxs-lookup"><span data-stu-id="f5b8e-105">Multiplies the coefficient in a `GeneratorIndex`.</span></span>

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="f5b8e-106">入力</span><span class="sxs-lookup"><span data-stu-id="f5b8e-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="f5b8e-107">乗数: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f5b8e-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f5b8e-108">係数の乗数。</span><span class="sxs-lookup"><span data-stu-id="f5b8e-108">The multiplier on the coefficient.</span></span>


### <a name="generatorindex--generatorindex"></a><span data-ttu-id="f5b8e-109">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f5b8e-109">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f5b8e-110">乗算する `GeneratorIndex`。</span><span class="sxs-lookup"><span data-stu-id="f5b8e-110">The `GeneratorIndex` to be multiplied.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="f5b8e-111">出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f5b8e-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f5b8e-112">係数が係数 `GeneratorIndex` である用語を表す `multiplier` 。</span><span class="sxs-lookup"><span data-stu-id="f5b8e-112">A `GeneratorIndex` representing a term with coefficient a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5b8e-113">参照</span><span class="sxs-lookup"><span data-stu-id="f5b8e-113">See Also</span></span>

- [<span data-ttu-id="f5b8e-114">GeneratorIndex です。</span><span class="sxs-lookup"><span data-stu-id="f5b8e-114">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)