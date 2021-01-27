---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: a3658bbf62068c9eea2d9b763cbff5596f426135
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854972"
---
# <a name="localrotationslayer-function"></a>LocalRotationsLayer 関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


指定された軸に沿って非制御 (単 qubit) の回転の配列を返します。レジスタ内の qubit ごとに1つの回転があり、個別のモデルパラメーターによってパラメーター化されます。

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>入力

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

指定したレイヤーによって操作された qubits の数。


### <a name="axis--pauli"></a>axis: [P# li](xref:microsoft.quantum.lang-ref.pauli)

指定されたレイヤー内の各回転の回転軸。



## <a name="output--controlledrotation"></a>出力: [Controlle入力](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

指定された軸についての制御された回転の配列 (各 qubits に1つ) `nQubits` 。