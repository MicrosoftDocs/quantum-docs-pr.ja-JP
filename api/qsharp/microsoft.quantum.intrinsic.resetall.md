---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetAll 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: d22ce607e8e5cb3a1c041dc1973875f2a0777d2b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198692"
---
# <a name="resetall-operation"></a>ResetAll 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


Qubits の配列を指定した場合は、それらを測定し、安全に解放できるように、それらが | 0 ⟩状態であることを確認します。

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

状態が $ \ket $ にリセットされる qubits の配列 {0} 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

