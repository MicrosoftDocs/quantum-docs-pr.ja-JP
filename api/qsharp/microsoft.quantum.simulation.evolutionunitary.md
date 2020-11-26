---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: EvolutionUnitary ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 38e7da28d4146df9cc132ad69ee939c44bc917f7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225263"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="1ac5a-102">EvolutionUnitary ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="1ac5a-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="1ac5a-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1ac5a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1ac5a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1ac5a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1ac5a-105">ユニタリ時間の進化演算子を表します。</span><span class="sxs-lookup"><span data-stu-id="1ac5a-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="1ac5a-106">1つ目のパラメーターは、時間の進化の期間であり、2番目のパラメーターは、ユニタリによって実行される qubit レジスタです。</span><span class="sxs-lookup"><span data-stu-id="1ac5a-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

