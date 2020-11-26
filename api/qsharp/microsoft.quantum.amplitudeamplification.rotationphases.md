---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191365"
---
# <a name="rotationphases-user-defined-type"></a>RotationPhases ユーザー定義型

名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


振幅増幅での単一 qubit 回転のシーケンスのフェーズ。

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>解説

1つ目のパラメーターは、反射のフェーズの配列であり、単 qubit 回転の積として表現されます。
[ G.H. 低、I. L。 語, https://arxiv.org/abs/1707.05391 ] を入力します。