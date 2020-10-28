---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetAll 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 00b7c0f508d76fb0f5b46c7ec00c0718469365a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711412"
---
# <a name="resetall-operation"></a>ResetAll 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

パック [](https://nuget.org/packages/)


Qubits の配列を指定した場合は、それらを測定し、安全に解放できるように、それらが | 0 ⟩状態であることを確認します。

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

状態が $ \ket $ にリセットされる qubits の配列 {0} 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

