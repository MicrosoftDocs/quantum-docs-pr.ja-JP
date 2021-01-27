---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843961"
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