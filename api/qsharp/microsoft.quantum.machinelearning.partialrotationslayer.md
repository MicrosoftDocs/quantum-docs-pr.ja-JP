---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ade0640b07f633982e98d5d02239fa205909bcce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196244"
---
# <a name="partialrotationslayer-function"></a>PartialRotationsLayer 関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


個別のモデルパラメーターによってパラメーター化された、指定した軸に沿った単一の qubit 回転の配列を返します。

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>入力

### <a name="idxsqubits--int"></a>idxsQubits: [Int](xref:microsoft.quantum.lang-ref.int)[]

各回転のターゲットとして使用される qubits のインデックス。


### <a name="axis--pauli"></a>axis: [P# li](xref:microsoft.quantum.lang-ref.pauli)

指定されたレイヤー内の各回転の回転軸。



## <a name="output--controlledrotation"></a>出力: [Controlle入力](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

指定された軸についての制御された回転の配列 (各 qubits に1つ) `nQubits` 。