---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: サンプリングされた関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854941"
---
# <a name="sampled-function"></a>サンプリングされた関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

