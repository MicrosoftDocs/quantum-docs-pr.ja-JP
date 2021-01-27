---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionFunction
title: JordanWignerFermionFunction 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: a1c0b56e18f3adfb6c413880cc0c155741a3255a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98838874"
---
# <a name="jordanwignerfermionfunction-function"></a><span data-ttu-id="e1b0a-102">JordanWignerFermionFunction 関数</span><span class="sxs-lookup"><span data-stu-id="e1b0a-102">JordanWignerFermionFunction function</span></span>

<span data-ttu-id="e1b0a-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e1b0a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e1b0a-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e1b0a-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="e1b0a-105">Dynamical generator を simulatable ゲートと JordanWigner ベースの拡張のセットとして表します。</span><span class="sxs-lookup"><span data-stu-id="e1b0a-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function JordanWignerFermionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="e1b0a-106">入力</span><span class="sxs-lookup"><span data-stu-id="e1b0a-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="e1b0a-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e1b0a-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e1b0a-108">JordanWigner での、ユニタリの発展として表現されるジェネレーターインデックス。</span><span class="sxs-lookup"><span data-stu-id="e1b0a-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="e1b0a-109">出力: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="e1b0a-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="e1b0a-110">`EvolutionUnitary`' GeneratorIndex ' で参照されている用語による時間の推移を表す。</span><span class="sxs-lookup"><span data-stu-id="e1b0a-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>