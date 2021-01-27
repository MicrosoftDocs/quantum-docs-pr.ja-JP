---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorSystem
title: IdentityGeneratorSystem 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorSystem
qsharp.summary: Returns a generator system consistent with the zero Hamiltonian `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 6602087cf7fa173a28fc5894f39ec02a67802427
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858133"
---
# <a name="identitygeneratorsystem-function"></a>IdentityGeneratorSystem 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Id 進化操作に対応する、ゼロ Hamiltonian と一貫性のあるジェネレーターシステムを返し `H = 0` ます。

```qsharp
function IdentityGeneratorSystem () : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="output--generatorsystem"></a>出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Hamiltonian $H = $0 での進化を表すジェネレーターシステム。