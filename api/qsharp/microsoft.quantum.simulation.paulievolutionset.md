---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 89c81aca4cfad6087d764ac8f5a0f1426e905e4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722047"
---
# <a name="paulievolutionset-function"></a><span data-ttu-id="f0b4b-102">PauliEvolutionSet 関数</span><span class="sxs-lookup"><span data-stu-id="f0b4b-102">PauliEvolutionSet function</span></span>

<span data-ttu-id="f0b4b-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f0b4b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f0b4b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f0b4b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f0b4b-105">Dynamical generator を simulatable ゲートのセットとして表し、拡張を p にします。</span><span class="sxs-lookup"><span data-stu-id="f0b4b-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="f0b4b-106">出力: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="f0b4b-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="f0b4b-107">`EvolutionSet` `GeneratorIndex` PEvolutionUnitary に対してを "" にマップする。</span><span class="sxs-lookup"><span data-stu-id="f0b4b-107">An `EvolutionSet` that maps a `GeneratorIndex` for the Pauli basis to an \`EvolutionUnitary.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0b4b-108">解説</span><span class="sxs-lookup"><span data-stu-id="f0b4b-108">Remarks</span></span>

<span data-ttu-id="f0b4b-109">これは、の部分的な適用によって取得され <xref:microsoft.quantum.simulation.paulievolutionfunction> ます。</span><span class="sxs-lookup"><span data-stu-id="f0b4b-109">This is obtained by partial application of <xref:microsoft.quantum.simulation.paulievolutionfunction>.</span></span>