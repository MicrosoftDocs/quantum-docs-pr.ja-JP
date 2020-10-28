---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: サンプリングされた関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722425"
---
# <a name="sampled-function"></a>サンプリングされた関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パック [](https://nuget.org/packages/)


指定されたスケジュールを使用して、指定された配列をサンプリングします。

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a>入力

### <a name="schedule--samplingschedule"></a>スケジュール: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

サンプリング値で使用するスケジュール。


### <a name="values--t"></a>値: ' t []

サンプリングする値の配列。



## <a name="output--t"></a>出力: ' t []

指定されたスケジュールに従った値からの要素の配列。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

