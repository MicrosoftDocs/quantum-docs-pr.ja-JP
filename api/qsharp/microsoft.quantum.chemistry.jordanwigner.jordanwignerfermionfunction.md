---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionFunction
title: JordanWignerFermionFunction 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 7d29393293acfc1748a1805f339951b1ff0f9b10
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714030"
---
# <a name="jordanwignerfermionfunction-function"></a><span data-ttu-id="78e12-102">JordanWignerFermionFunction 関数</span><span class="sxs-lookup"><span data-stu-id="78e12-102">JordanWignerFermionFunction function</span></span>

<span data-ttu-id="78e12-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="78e12-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="78e12-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="78e12-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="78e12-105">Dynamical generator を simulatable ゲートと JordanWigner ベースの拡張のセットとして表します。</span><span class="sxs-lookup"><span data-stu-id="78e12-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function JordanWignerFermionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="78e12-106">入力</span><span class="sxs-lookup"><span data-stu-id="78e12-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="78e12-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="78e12-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="78e12-108">JordanWigner での、ユニタリの発展として表現されるジェネレーターインデックス。</span><span class="sxs-lookup"><span data-stu-id="78e12-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="78e12-109">出力: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="78e12-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="78e12-110">`EvolutionUnitary`' GeneratorIndex ' で参照されている用語による時間の推移を表す。</span><span class="sxs-lookup"><span data-stu-id="78e12-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>