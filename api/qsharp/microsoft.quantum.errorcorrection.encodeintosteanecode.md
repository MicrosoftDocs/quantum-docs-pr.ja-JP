---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: EncodeIntoSteaneCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 2f65423a17dafadd1f9f10a07335150dfc8bf886
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826208"
---
# <a name="encodeintosteanecode-operation"></a>EncodeIntoSteaneCode 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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