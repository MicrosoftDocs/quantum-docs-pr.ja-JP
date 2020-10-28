---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ユーザー定義型の制御
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711361"
---
# <a name="controlledrotation-user-defined-type"></a>ユーザー定義型の制御

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パック [](https://nuget.org/packages/)


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