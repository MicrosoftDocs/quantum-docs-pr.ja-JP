---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: Applytofirst、"操作"
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: b01c1072306cfdebcb90827a14683a32312481fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850697"
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