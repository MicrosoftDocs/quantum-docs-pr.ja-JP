---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: ee8f3c0716f035dcb0c4fad557092fbf8dd3c356
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229411"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="2cc89-102">EvolutionSet ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="2cc89-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="2cc89-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2cc89-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2cc89-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2cc89-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2cc89-105">シミュレーションアルゴリズムを実装するために簡単に実装して使用できるゲートのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="2cc89-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="2cc89-106">セット内の要素は、によってインデックスが作成され、  <xref:microsoft.quantum.simulation.generatorindex> 各セットはからの関数によって記述され `GeneratorIndex` ます。これは  <xref:microsoft.quantum.simulation.evolutionunitary> 、時間を表す実数によってパラメーター化された操作です。</span><span class="sxs-lookup"><span data-stu-id="2cc89-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

