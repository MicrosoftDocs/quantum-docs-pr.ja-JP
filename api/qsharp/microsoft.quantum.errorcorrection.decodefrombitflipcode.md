---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: DecodeFromBitFlipCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: be6ad5fce9eeb3eea031ff301b78dbb3680b66f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712481"
---
# <a name="decodefrombitflipcode-operation"></a>DecodeFromBitFlipCode 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


[3, 1, 3]/⟦ 3, 1, 1 ⟧ビットフリップコードからデコードします。

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>入力

### <a name="logicalregister--logicalregister"></a>logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

ビットフリップコードのコードブロック。



## <a name="output--qubitqubit"></a>出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])

論理レジスタにエンコードされたデータの組と、より隣人を表すために使用される補助 qubits。

## <a name="see-also"></a>参照

- [Microsoft... ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [EncodeIntoBitFlipCode を修正します。](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)