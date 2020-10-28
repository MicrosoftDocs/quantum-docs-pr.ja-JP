---
uid: Microsoft.Quantum.Research.Chemistry.JordanWignerOptimizedFermionEvolutionSet
title: JordanWignerOptimizedFermionEvolutionSet 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JordanWignerOptimizedFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: d2d916655b7538b39d5739d67dbb3fc9920cf67a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722140"
---
# <a name="jordanwigneroptimizedfermionevolutionset-function"></a><span data-ttu-id="7fde9-102">JordanWignerOptimizedFermionEvolutionSet 関数</span><span class="sxs-lookup"><span data-stu-id="7fde9-102">JordanWignerOptimizedFermionEvolutionSet function</span></span>

<span data-ttu-id="7fde9-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7fde9-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="7fde9-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7fde9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7fde9-105">Dynamical generator を simulatable ゲートのセットとして表し、拡張を p にします。</span><span class="sxs-lookup"><span data-stu-id="7fde9-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function JordanWignerOptimizedFermionEvolutionSet (parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="input"></a><span data-ttu-id="7fde9-106">入力</span><span class="sxs-lookup"><span data-stu-id="7fde9-106">Input</span></span>

### <a name="parityqubit--qubit"></a><span data-ttu-id="7fde9-107">parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7fde9-107">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7fde9-108">タイム進化の符号を決定する qubit。</span><span class="sxs-lookup"><span data-stu-id="7fde9-108">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionset"></a><span data-ttu-id="7fde9-109">出力: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="7fde9-109">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="7fde9-110">`EvolutionSet` `GeneratorIndex` JWOptimized ベースのを ' EvolutionUnitary にマップする。</span><span class="sxs-lookup"><span data-stu-id="7fde9-110">An `EvolutionSet` that maps a `GeneratorIndex` for the JWOptimized basis to an \`EvolutionUnitary.</span></span>