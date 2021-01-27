---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: 回復した Css 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: c192abbdfd02b26fbdba7b11f51ed08bb1a2030f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853048"
---
# <a name="recovercss-operation"></a>回復した Css 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


型によって記述されたクォンタムコードによって、1回のエラー修正を実行し `CSS` ます。

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>入力

### <a name="code--css"></a>コード: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

クォンタム CSS エラー-型としてパッケージ化されたコードを修正すると、 `CSS` クォンタムデータのエンコードとデコード、およびエラー syndromes の測定方法が記述されます。


### <a name="fnx--recoveryfn"></a>fnX: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`各 $X $ error より隣人を、 `Pauli[]` 検出されたエラーを修正する操作にマップする。


### <a name="fnz--recoveryfn"></a>fnZ: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`各 $Z $ error より隣人を、 `Pauli[]` 検出されたエラーを修正する操作にマップする。


### <a name="logicalregister--logicalregister"></a>logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

安定板のコードが定義されている qubits の配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [Microsoft... ErrorCorrection .CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [Microsoft... ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [Microsoft... ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)