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
# <a name="identitytimedependentgeneratorsystem-function"></a>IdentityTimeDependentGeneratorSystem 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


Hamiltonian と一貫性のある時間に依存するジェネレーターシステムを返し `H(s) = 0` ます。

```qsharp
function IdentityTimeDependentGeneratorSystem () : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="output--timedependentgeneratorsystem"></a>出力: [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)

すべての $s $ の Hamiltonian $H = $0 の下での進化を表す、時間に依存するジェネレーターシステム。