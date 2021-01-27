---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: DefaultTrainingOptions 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856005"
---
# <a name="defaulttrainingoptions-function"></a>DefaultTrainingOptions 関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


トレーニング分類子の既定のオプションセットを返します。

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a>出力: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

分類子をトレーニングするときに使用する、既定のトレーニングオプションの適切なセット。

## <a name="example"></a>例

既定のオプションを使用するが、追加の測定値を使用するには、演算子を使用し `w/` ます。

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```