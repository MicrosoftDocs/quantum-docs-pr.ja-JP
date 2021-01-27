---
uid: Microsoft.Quantum.Simulation.IdentityTimeDependentGeneratorSystem
title: IdentityTimeDependentGeneratorSystem 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a time-dependent generator system consistent with the Hamiltonian `H(s) = 0`.
ms.openlocfilehash: e25e01a1f16182ea55fabd325d200c8489df5953
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846802"
---
# <a name="identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="1a651-102">IdentityTimeDependentGeneratorSystem 関数</span><span class="sxs-lookup"><span data-stu-id="1a651-102">IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="1a651-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1a651-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1a651-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1a651-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1a651-105">Hamiltonian と一貫性のある時間に依存するジェネレーターシステムを返し `H(s) = 0` ます。</span><span class="sxs-lookup"><span data-stu-id="1a651-105">Returns a time-dependent generator system consistent with the Hamiltonian `H(s) = 0`.</span></span>

```qsharp
function IdentityTimeDependentGeneratorSystem () : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="1a651-106">出力: [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="1a651-106">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="1a651-107">すべての $s $ の Hamiltonian $H = $0 の下での進化を表す、時間に依存するジェネレーターシステム。</span><span class="sxs-lookup"><span data-stu-id="1a651-107">A time dependent generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>