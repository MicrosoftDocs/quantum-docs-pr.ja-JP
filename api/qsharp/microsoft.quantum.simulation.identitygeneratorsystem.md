---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorSystem
title: IdentityGeneratorSystem 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorSystem
qsharp.summary: Returns a generator system consistent with the zero Hamiltonian `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 251d0ae23a61d20f6d7a8d6b7c9f86f543886c52
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724525"
---
# <a name="identitygeneratorsystem-function"></a>IdentityGeneratorSystem 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


Id 進化操作に対応する、ゼロ Hamiltonian と一貫性のあるジェネレーターシステムを返し `H = 0` ます。

```qsharp
function IdentityGeneratorSystem () : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="output--generatorsystem"></a>出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Hamiltonian $H = $0 での進化を表すジェネレーターシステム。