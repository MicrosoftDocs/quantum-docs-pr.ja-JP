---
uid: Microsoft.Quantum.Simulation.EvolutionGenerator
title: EvolutionGenerator ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionGenerator
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.

  Last parameter for number of terms.
ms.openlocfilehash: be741216bf99305bf5f1d149c815e98aba36aad1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710633"
---
# <a name="evolutiongenerator-user-defined-type"></a><span data-ttu-id="cf42d-102">EvolutionGenerator ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="cf42d-102">EvolutionGenerator user defined type</span></span>

<span data-ttu-id="cf42d-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="cf42d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="cf42d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cf42d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cf42d-105">Dynamical generator を simulatable ゲートのセットとして表し、拡張をその基準として表します。</span><span class="sxs-lookup"><span data-stu-id="cf42d-105">Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.</span></span>

<span data-ttu-id="cf42d-106">使用条件の最後のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="cf42d-106">Last parameter for number of terms.</span></span>

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```

