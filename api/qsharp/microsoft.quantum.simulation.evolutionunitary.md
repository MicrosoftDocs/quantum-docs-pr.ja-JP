---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: EvolutionUnitary ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 28ab492573b67e4aa42392e4ee499596b9c0225f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724856"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="59487-102">EvolutionUnitary ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="59487-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="59487-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="59487-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="59487-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="59487-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="59487-105">ユニタリ時間の進化演算子を表します。</span><span class="sxs-lookup"><span data-stu-id="59487-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="59487-106">1つ目のパラメーターは、時間の進化の期間であり、2番目のパラメーターは、ユニタリによって実行される qubit レジスタです。</span><span class="sxs-lookup"><span data-stu-id="59487-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

