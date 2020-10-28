---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: AssertAllZeroWithinTolerance 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 5e401904086323fabef7914d34463f50e4c38862
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713041"
---
# <a name="assertallzerowithintolerance-operation"></a>AssertAllZeroWithinTolerance 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


指定された qubits のアサートはすべて、指定された許容範囲内の $ \ket {0} $ 状態にあります。

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit
```


## <a name="input"></a>入力

### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket $ 状態になるようにアサートされた qubits {0} 。


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

状態を $ \ket $ 状態にするための精度 {0}



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [AssertQubitWithinTolerance です。](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)