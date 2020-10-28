---
uid: Microsoft.Quantum.Simulation.IdxToCoeff
title: IdxToCoeff 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToCoeff
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: 50e0c536b01cddb56482580fd634270c4e104173
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724511"
---
# <a name="idxtocoeff-function"></a>IdxToCoeff 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


の実装で使用されます。 `PauliBlockEncoding`

```qsharp
function IdxToCoeff (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToCoeff : (Microsoft.Quantum.Simulation.GeneratorIndex -> Double)) : Double
```


## <a name="input"></a>入力

### <a name="idx--int"></a>idx: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="genfun--int---generatorindex"></a>genfun: [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)




### <a name="genidxtocoeff--generatorindex---double"></a>genIdxToCoeff: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="see-also"></a>参照

- [Microsoft... シミュレーションのエンコード](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)