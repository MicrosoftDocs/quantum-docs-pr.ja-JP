---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 1aeab429bd6304c621e0d5225b43a76eab607c84
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209198"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a>ApplyMultiplyControlledLowDepthAnd 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ターゲット qubit が初期化されていることを前提として、複数の制御を行う Toffoli ゲートを実装します。  Adjoint 操作では、ターゲットの qubit が0にリセットされることを前提としています。  Rz の深さは1である必要がありますが、ヘルパーの qubits の数は qubits の数で指数で表示されます。

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a>入力

### <a name="controls--qubit"></a>コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

制御 qubits


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

ターゲット qubit



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

