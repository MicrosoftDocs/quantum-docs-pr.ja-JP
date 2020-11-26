---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: Applytofirst二つ Qubitsca 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: a2281776b617d5c3f8cc706ea09d14995fce4a27
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208654"
---
# <a name="applytofirsttwoqubitsca-operation"></a>Applytofirst二つ Qubitsca 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


レジスタ内の最初の2つの qubits に操作を適用します。
修飾子は、 `CA` 操作が制御可能であり、adjointable であることを示します。

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="op--qubitqubit--unit--is-adj--ctl"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl

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