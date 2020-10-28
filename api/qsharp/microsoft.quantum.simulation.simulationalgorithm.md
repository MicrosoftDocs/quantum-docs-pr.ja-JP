---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: SimulationAlgorithm ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: 9127a936bbf7a212e712645eabdf49fefc7a97d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725570"
---
# <a name="simulationalgorithm-user-defined-type"></a>SimulationAlgorithm ユーザー定義型

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


時間に依存しないシミュレーションアルゴリズムを表します。

時間に依存しないシミュレーション手法では、 <xref:microsoft.quantum.simulation.evolutiongenerator>
ある期間の時間の進化を時間単位で指定します。

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```

