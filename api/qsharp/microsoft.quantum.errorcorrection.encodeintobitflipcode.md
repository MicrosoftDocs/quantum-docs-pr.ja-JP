---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: EncodeIntoBitFlipCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712406"
---
# <a name="encodeintobitflipcode-operation"></a>EncodeIntoBitFlipCode 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


[3, 1, 3]/⟦ 3, 1, 1 ⟧ビットフリップコードにエンコードされます。

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>入力

### <a name="physregister--qubit"></a>physRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

保護されるデータを表す物理 qubits のレジスタ。


### <a name="auxqubits--qubit"></a>auxQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

{00}保護されるデータのエンコードに使用される、$ \ket $ 状態の最初の補助 qubits のレジスタ。



## <a name="output--logicalregister"></a>出力: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

エンコーディングで使用される物理および補助 qubits。論理レジスタとして表されます。

## <a name="see-also"></a>参照

- [Microsoft... ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)