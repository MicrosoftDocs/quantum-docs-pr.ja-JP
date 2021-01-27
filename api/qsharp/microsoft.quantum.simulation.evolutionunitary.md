---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: EvolutionUnitary ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: ea160bb9a0a8bb5106c3e37a6a16155bad71dd25
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856057"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="5862f-102">EvolutionUnitary ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="5862f-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="5862f-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5862f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5862f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5862f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5862f-105">ユニタリ時間の進化演算子を表します。</span><span class="sxs-lookup"><span data-stu-id="5862f-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="5862f-106">1つ目のパラメーターは、時間の進化の期間であり、2番目のパラメーターは、ユニタリによって実行される qubit レジスタです。</span><span class="sxs-lookup"><span data-stu-id="5862f-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

