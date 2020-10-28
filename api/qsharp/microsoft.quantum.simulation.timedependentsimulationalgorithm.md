---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: TimeDependentSimulationAlgorithm ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: 9d2a1a853005495b5a9df60ac1f0dcbfbdf7637f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725752"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="86a9b-102">TimeDependentSimulationAlgorithm ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="86a9b-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="86a9b-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="86a9b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="86a9b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="86a9b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="86a9b-105">時間に依存するシミュレーションアルゴリズムを表します。</span><span class="sxs-lookup"><span data-stu-id="86a9b-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="86a9b-106">時間に依存するシミュレーション手法では、 <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="86a9b-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="86a9b-107">ある期間の時間の進化を時間単位で示します。</span><span class="sxs-lookup"><span data-stu-id="86a9b-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

