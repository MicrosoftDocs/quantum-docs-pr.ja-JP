---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723288"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize 関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パック [](https://nuget.org/packages/)


特定の特徴ベクターをエンコードするために必要な qubits の数を返します。

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>入力

### <a name="sample--double"></a>サンプル: [Double](xref:microsoft.quantum.lang-ref.double)[]

Qubit レジスタにエンコードされるサンプルの特徴ベクトル。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

Qubit レジスタにエンコードするために必要なサイズ `sample` (qubit の数として表現)。