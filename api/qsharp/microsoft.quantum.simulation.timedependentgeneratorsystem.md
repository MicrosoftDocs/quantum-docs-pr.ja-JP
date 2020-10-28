---
uid: Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
title: TimeDependentGeneratorSystem ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentGeneratorSystem
qsharp.summary: Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.
ms.openlocfilehash: 144a44448c9fda7a038b17ac7c49f63e8cc4dd55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719875"
---
# <a name="timedependentgeneratorsystem-user-defined-type"></a><span data-ttu-id="7338e-102">TimeDependentGeneratorSystem ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="7338e-102">TimeDependentGeneratorSystem user defined type</span></span>

<span data-ttu-id="7338e-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7338e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7338e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7338e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7338e-105">時間に依存する dynamical ジェネレーターを、time から dynamical generator の値までの関数として表します。</span><span class="sxs-lookup"><span data-stu-id="7338e-105">Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.</span></span>

```qsharp

newtype TimeDependentGeneratorSystem = ((Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

