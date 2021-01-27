---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848441"
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