---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721767"
---
# <a name="rotationphases-user-defined-type"></a>RotationPhases ユーザー定義型

名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

パック [](https://nuget.org/packages/)


振幅増幅での単一 qubit 回転のシーケンスのフェーズ。

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>解説

1つ目のパラメーターは、反射のフェーズの配列であり、単 qubit 回転の積として表現されます。
[ G.H. 低、I. L。 語, https://arxiv.org/abs/1707.05391 ] を入力します。