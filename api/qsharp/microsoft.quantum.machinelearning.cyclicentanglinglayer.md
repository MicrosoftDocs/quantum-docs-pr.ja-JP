---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720511"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer 関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パック [](https://nuget.org/packages/)


指定された軸に沿って1つの制御された回転の配列を返します。 qubits のレジスタで周期的に配置され、個別のモデルパラメーターによってパラメーター化されます。

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>入力

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

指定したレイヤーによって操作された qubits の数。


### <a name="axis--pauli"></a>axis: [P# li](xref:microsoft.quantum.lang-ref.pauli)

指定されたレイヤー内の各回転の回転軸。


### <a name="stride--int"></a>stride: [Int](xref:microsoft.quantum.lang-ref.int)

各回転のターゲットと制御のインデックスを分離する。



## <a name="output--controlledrotation"></a>出力: [Controlle入力](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Qubit のレジスタ間で周期的に配置された、2つの qubit 制御された回転の配列 `nQubits` 。