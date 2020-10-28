---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 212ed4c473fab3572f73ea250061057ad13e393f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709438"
---
# <a name="interpolategeneratorsystemsimpl-function"></a>InterpolateGeneratorSystemsImpl 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


`GeneratorSystems`0 から1までのスケジュールパラメーターに従って、2つの間を直線的に補間 `s` します。

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>入力

### <a name="schedule--double"></a>schedule: [Double](xref:microsoft.quantum.lang-ref.double)

スケジュールパラメーター $s \ [0, 1] $。


### <a name="generatorsystemstart--generatorsystem"></a>generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

開始 `GeneratorSystem` 。


### <a name="generatorsystemend--generatorsystem"></a>generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

最後 `GeneratorSystem` 。



## <a name="output--generatorsystem"></a>出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`入力ジェネレーターシステムの合計であり、weight $ (1-s) $ on `generatorSystemStart` および weight $s $ on のシステムを表す `generatorSystemEnd` 。

## <a name="see-also"></a>参照

- [GeneratorSystem です。](xref:Microsoft.Quantum.Simulation.GeneratorSystem)