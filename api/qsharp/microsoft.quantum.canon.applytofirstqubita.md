---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: ApplyToFirstQubitA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 4f0b209988c01076bdd0429d36d98c8060141618
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208841"
---
# <a name="applytofirstqubita-operation"></a>ApplyToFirstQubitA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


レジスタ内の最初の qubit に操作を適用します。
修飾子は、 `A` 操作が adjointable であることを示します。

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>入力

### <a name="op--qubit--unit--is-adj"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

最初の qubit に適用する操作


### <a name="register--qubit"></a>register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

操作が適用されている最初の qubit への qubit 配列



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [Microsoft... "."。](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)