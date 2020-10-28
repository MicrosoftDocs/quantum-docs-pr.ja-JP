---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: 回復操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: a659399f51794a4edc1d2ff43da84e46797103fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712210"
---
# <a name="recover-operation"></a>回復操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


型によって記述されたクォンタムコードによって、1回のエラー修正を実行し `QECC` ます。

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>入力

### <a name="code--qecc"></a>コード: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)

クォンタムエラー-型としてパッケージ化されたコードを修正するには、 `QECC` クォンタムデータのエンコードとデコード、およびエラー syndromes の測定方法を記述します。


### <a name="fn--recoveryfn"></a>fn: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn` `Pauli[]` 検出されたエラーを修正する操作に各エラーより隣人をマップする。


### <a name="logicalregister--logicalregister"></a>logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

安定板のコードが定義されている qubits の配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [Microsoft... ErrorCorrection. QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [Microsoft... ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [Microsoft... ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)