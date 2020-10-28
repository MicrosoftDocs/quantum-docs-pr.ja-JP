---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionEvolutionSet
title: JordanWignerFermionEvolutionSet 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: a43f9c27eb1e60fb072d5962c37816577a7b2879
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714035"
---
# <a name="jordanwignerfermionevolutionset-function"></a><span data-ttu-id="cb9b0-102">JordanWignerFermionEvolutionSet 関数</span><span class="sxs-lookup"><span data-stu-id="cb9b0-102">JordanWignerFermionEvolutionSet function</span></span>

<span data-ttu-id="cb9b0-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="cb9b0-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="cb9b0-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb9b0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb9b0-105">Dynamical generator を simulatable ゲートと JordanWigner ベースの拡張のセットとして表します。</span><span class="sxs-lookup"><span data-stu-id="cb9b0-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function JordanWignerFermionEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="cb9b0-106">出力: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="cb9b0-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="cb9b0-107">`EvolutionSet` `GeneratorIndex` JordanWigner ベースのを ' EvolutionUnitary にマップする。</span><span class="sxs-lookup"><span data-stu-id="cb9b0-107">An `EvolutionSet` that maps a `GeneratorIndex` for the JordanWigner basis to an \`EvolutionUnitary.</span></span>