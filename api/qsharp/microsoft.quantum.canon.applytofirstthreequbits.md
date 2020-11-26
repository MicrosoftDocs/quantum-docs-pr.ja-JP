---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: Applytofirst、"操作"
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 5572bd2a096a4f9bdb1153ae80950ae854965b82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217460"
---
# <a name="applytofirstthreequbits-operation"></a>Applytofirst、"操作"

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


レジスタ内の最初の3つの qubits に操作を適用します。

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="op--qubitqubitqubit--unit"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)、[qubit](xref:microsoft.quantum.lang-ref.qubit)、[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

最初の3つの qubits に適用する操作


### <a name="register--qubit"></a>register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

操作が適用される最初の3つの qubit への qubit 配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

このようにすると、次の記述と同じ結果が得られます。

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a>参照

- [Microsoft......。](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [Microsoft.........................](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [Microsoft.........................](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)