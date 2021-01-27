---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: Applytofirst二つ Qubitsa 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 197f1da6682b100a0b71f3548727188c0ef6f7c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850678"
---
# <a name="applytofirsttwoqubitsa-operation"></a>Applytofirst二つ Qubitsa 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


レジスタ内の最初の2つの qubits に操作を適用します。
修飾子は、 `A` 操作が adjointable であることを示します。

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>入力

### <a name="op--qubitqubit--unit--is-adj"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞

最初の2つの qubits に適用する操作


### <a name="register--qubit"></a>register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

操作が適用される最初の2つの qubit への qubit 配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

このようにすると、次の記述と同じ結果が得られます。

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a>参照

- [Microsoft. Canon. Applytofirstの場合](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)