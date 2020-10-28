---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: DecodeFromFiveQubitCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 421da6296b604f30aefed58730091f64f19c3a61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712467"
---
# <a name="decodefromfivequbitcode-operation"></a>DecodeFromFiveQubitCode 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


⟦ 5, 1, 3 ⟧クォンタムコードをデコードします。

```qsharp
operation DecodeFromFiveQubitCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>入力

### <a name="logicalregister--logicalregister"></a>logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

エンコードされた 5-qubits コードの論理状態を表す qubits の配列。



## <a name="output--qubitqubit"></a>出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])

2番目のパラメーターの補助 qubit と共に、最初のパラメーターのエンコードされていない状態を表す、値1の qubit 配列。

## <a name="see-also"></a>参照

- [Microsoft... Fivvldb Bitcodeencoder](xref:Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder)
- [Microsoft... ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)