---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: EncodeIntoSteaneCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 39b8ab549413d9d5281f6b84a6e970c45242fca8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712392"
---
# <a name="encodeintosteanecode-operation"></a>EncodeIntoSteaneCode 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


エンコードされていないクォンタムレジスタを⟦7、1、3⟧ Steane 量子コードでエンコードされたクォンタムレジスタにマップするエンコーディング操作。

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>入力

### <a name="physregister--qubit"></a>physRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

エンコードされていないクォンタム状態を保持する qubit レジスタ


### <a name="auxqubits--qubit"></a>auxQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

最初は0で、エンコーディング操作を実行できるようにクォンタムシステムに追加される qubit レジスタ。



## <a name="output--logicalregister"></a>出力: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Steane encoder が適用された後の状態を保持するクォンタムレジスタ

## <a name="see-also"></a>参照

- [Microsoft... ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [SteaneCodeDecoder を修正します。](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)