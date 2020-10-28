---
uid: Microsoft.Quantum.Simulation.IdentityTimeDependentGeneratorSystem
title: IdentityTimeDependentGeneratorSystem 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a time-dependent generator system consistent with the Hamiltonian `H(s) = 0`.
ms.openlocfilehash: d51794aacbcf13ab567ff6be4f5d6b04581833bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724520"
---
# <a name="identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="7fb3a-102">IdentityTimeDependentGeneratorSystem 関数</span><span class="sxs-lookup"><span data-stu-id="7fb3a-102">IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="7fb3a-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7fb3a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7fb3a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7fb3a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7fb3a-105">Hamiltonian と一貫性のある時間に依存するジェネレーターシステムを返し `H(s) = 0` ます。</span><span class="sxs-lookup"><span data-stu-id="7fb3a-105">Returns a time-dependent generator system consistent with the Hamiltonian `H(s) = 0`.</span></span>

```qsharp
function IdentityTimeDependentGeneratorSystem () : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="7fb3a-106">出力: [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="7fb3a-106">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="7fb3a-107">すべての $s $ の Hamiltonian $H = $0 の下での進化を表す、時間に依存するジェネレーターシステム。</span><span class="sxs-lookup"><span data-stu-id="7fb3a-107">A time dependent generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>