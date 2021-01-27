---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846978"
---
# <a name="labeledsample-user-defined-type"></a>LabeledSample ユーザー定義型

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


このサンプルが属するクラスでラベル付けされたサンプル。

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>名前付き項目

### <a name="features--double"></a>特徴: [Double](xref:microsoft.quantum.lang-ref.double)[]

指定されたサンプルの特徴のベクター。
### <a name="label--int"></a>ラベル: [Int](xref:microsoft.quantum.lang-ref.int)

このサンプルが属するクラスの整数ラベル。