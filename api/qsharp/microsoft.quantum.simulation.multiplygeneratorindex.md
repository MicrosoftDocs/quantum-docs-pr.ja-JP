---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: dc2bd02c40b53eca726f70578e3c5918add8f1bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230448"
---
# <a name="multiplygeneratorindex-function"></a><span data-ttu-id="2c8d2-102">MultiplyGeneratorIndex 関数</span><span class="sxs-lookup"><span data-stu-id="2c8d2-102">MultiplyGeneratorIndex function</span></span>

<span data-ttu-id="2c8d2-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2c8d2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2c8d2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2c8d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2c8d2-105">内の係数を乗算 `GeneratorIndex` します。</span><span class="sxs-lookup"><span data-stu-id="2c8d2-105">Multiplies the coefficient in a `GeneratorIndex`.</span></span>

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="2c8d2-106">入力</span><span class="sxs-lookup"><span data-stu-id="2c8d2-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="2c8d2-107">乗数: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2c8d2-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2c8d2-108">係数の乗数。</span><span class="sxs-lookup"><span data-stu-id="2c8d2-108">The multiplier on the coefficient.</span></span>


### <a name="generatorindex--generatorindex"></a><span data-ttu-id="2c8d2-109">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2c8d2-109">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="2c8d2-110">乗算する `GeneratorIndex`。</span><span class="sxs-lookup"><span data-stu-id="2c8d2-110">The `GeneratorIndex` to be multiplied.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="2c8d2-111">出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2c8d2-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="2c8d2-112">係数が係数 `GeneratorIndex` である用語を表す `multiplier` 。</span><span class="sxs-lookup"><span data-stu-id="2c8d2-112">A `GeneratorIndex` representing a term with coefficient a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c8d2-113">参照</span><span class="sxs-lookup"><span data-stu-id="2c8d2-113">See Also</span></span>

- [<span data-ttu-id="2c8d2-114">GeneratorIndex です。</span><span class="sxs-lookup"><span data-stu-id="2c8d2-114">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)