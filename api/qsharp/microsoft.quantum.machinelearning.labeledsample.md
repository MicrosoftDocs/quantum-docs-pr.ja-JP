---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196329"
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