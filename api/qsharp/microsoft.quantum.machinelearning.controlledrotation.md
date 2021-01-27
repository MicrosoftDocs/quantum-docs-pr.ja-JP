---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ユーザー定義型の制御
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847393"
---
# <a name="controlledrotation-user-defined-type"></a>ユーザー定義型の制御

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


ターゲットと制御のインデックス、回転軸、およびモデルパラメーターベクターへのインデックスに関して、制御されたローテーションについて説明します。

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a>名前付き項目

### <a name="targetindex--int"></a>TargetIndex: [Int](xref:microsoft.quantum.lang-ref.int)

この制御された回転のターゲット qubit のインデックス。
### <a name="controlindices--int"></a>ControlIndices: [Int](xref:microsoft.quantum.lang-ref.int)[]

この回転のためのコントロール qubit インデックスの配列。
### <a name="axis--pauli"></a>Axis: [P# li](xref:microsoft.quantum.lang-ref.pauli)

この回転の軸。
### <a name="parameterindex--int"></a>ParameterIndex: [Int](xref:microsoft.quantum.lang-ref.int)

この回転の角度を説明するモデルパラメーターベクターのインデックス。

## <a name="example"></a>例

次の例は、レジスタ内の最初の qubit の $X $ 軸についての回転と、2番目の qubit で制御され、シーケンシャルモデルの4番目のパラメーターによって指定された角度を表します。

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a>解説

制御されないローテーションは `ControlIndices` 、インデックスの空の配列にを設定することによって表すことができ `new Int[0]` ます。