---
uid: Microsoft.Quantum.Preparation._ApproximatelyUnprepareArbitraryStatePlan
title: _ApproximatelyUnprepareArbitraryStatePlan 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: _ApproximatelyUnprepareArbitraryStatePlan
qsharp.summary: Implementation step of arbitrary state preparation procedure.
ms.openlocfilehash: 4050a65b0830da4c3d73e84942780aa7c2643c76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724203"
---
# <a name="_approximatelyunpreparearbitrarystateplan-function"></a>_ApproximatelyUnprepareArbitraryStatePlan 関数

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パック [](https://nuget.org/packages/)


任意の状態の準備手順の実装手順。

```qsharp
function _ApproximatelyUnprepareArbitraryStatePlan (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], (rngControl : Range, idxTarget : Int)) : (Qubit[] => Unit is Adj + Ctl)[]
```


## <a name="input"></a>入力

### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="coefficients--complexpolar"></a>係数: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]




### <a name="rngcontrol--range"></a>rngControl: [範囲](xref:microsoft.quantum.lang-ref.range)




### <a name="idxtarget--int"></a>idxTarget: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--qubit--unit-adj--ctl"></a>出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl []



## <a name="see-also"></a>参照

- [PrepareArbitraryState の準備](xref:Microsoft.Quantum.Preparation.PrepareArbitraryState)
- [Microsoft. Canon....](xref:Microsoft.Quantum.Canon.MultiplexPauli)