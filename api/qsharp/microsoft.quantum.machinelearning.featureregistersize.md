---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196414"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize 関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


特定の特徴ベクターをエンコードするために必要な qubits の数を返します。

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>入力

### <a name="sample--double"></a>サンプル: [Double](xref:microsoft.quantum.lang-ref.double)[]

Qubit レジスタにエンコードされるサンプルの特徴ベクトル。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

Qubit レジスタにエンコードするために必要なサイズ `sample` (qubit の数として表現)。