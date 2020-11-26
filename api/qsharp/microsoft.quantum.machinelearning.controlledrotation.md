---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ユーザー定義型の制御
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 1e664b470caeba656ea4a73f70bbc0ef5fe76f7e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196567"
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

## <a name="remarks"></a>解説

制御されないローテーションは `ControlIndices` 、インデックスの空の配列にを設定することによって表すことができ `new Int[0]` ます。