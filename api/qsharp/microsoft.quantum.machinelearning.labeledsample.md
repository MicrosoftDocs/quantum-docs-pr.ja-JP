---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711333"
---
# <a name="labeledsample-user-defined-type"></a>LabeledSample ユーザー定義型

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パック [](https://nuget.org/packages/)


このサンプルが属するクラスでラベル付けされたサンプル。

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>名前付き項目

### <a name="features--double"></a>特徴: [Double](xref:microsoft.quantum.lang-ref.double)[]

指定されたサンプルの特徴のベクター。
### <a name="label--int"></a>ラベル: [Int](xref:microsoft.quantum.lang-ref.int)

このサンプルが属するクラスの整数ラベル。