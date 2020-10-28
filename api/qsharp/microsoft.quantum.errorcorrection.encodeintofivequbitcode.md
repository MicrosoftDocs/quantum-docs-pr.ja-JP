---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712397"
---
# <a name="encodeintofivequbitcode-operation"></a>EncodeIntoFiveQubitCode 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


⟦ 5, 1, 3 ⟧クォンタムコードにエンコードします。

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>入力

### <a name="physregister--qubit"></a>physRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

エンコード前の状態を表す qubit。 この配列 `Qubit[]` の長さは1です。


### <a name="auxqubits--qubit"></a>auxQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

エンコードされた状態を表すために使用される補助 qubits のレジスタ。



## <a name="output--logicalregister"></a>出力: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

エンコードされた `LogicalRegister` 状態を格納する型の物理 qubits の配列。

## <a name="see-also"></a>参照

- [Microsoft... ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)