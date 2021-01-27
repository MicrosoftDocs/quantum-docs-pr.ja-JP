---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 35c0b24da284a5871fd11b6d624102b853b89d19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856069"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="022d5-102">EvolutionSet ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="022d5-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="022d5-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="022d5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="022d5-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="022d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="022d5-105">シミュレーションアルゴリズムを実装するために簡単に実装して使用できるゲートのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="022d5-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="022d5-106">セット内の要素は、によってインデックスが作成され、  <xref:microsoft.quantum.simulation.generatorindex> 各セットはからの関数によって記述され `GeneratorIndex` ます。これは  <xref:microsoft.quantum.simulation.evolutionunitary> 、時間を表す実数によってパラメーター化された操作です。</span><span class="sxs-lookup"><span data-stu-id="022d5-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

