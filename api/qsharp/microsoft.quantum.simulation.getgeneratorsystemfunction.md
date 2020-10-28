---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 60ebbdbd1020d41a54426377043fc0c84ceec504
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724553"
---
# <a name="getgeneratorsystemfunction-function"></a>GetGeneratorSystemFunction 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


`GeneratorIndex`内の関数を取得 `GeneratorSystem` します。

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a>入力

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

目的の `GeneratorSystem`。



## <a name="output--int---generatorindex"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Hamiltonian 内の各用語にインデックスを付けた関数 `GeneratorIndex` 。

## <a name="see-also"></a>参照

- [GeneratorIndex です。](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [GeneratorSystem です。](xref:Microsoft.Quantum.Simulation.GeneratorSystem)