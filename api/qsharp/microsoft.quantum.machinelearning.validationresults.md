---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 42bfab7fd1f9372d9394f2eaf2d698b39b4307e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211493"
---
# <a name="validationresults-user-defined-type"></a>ValidationResults ユーザー定義型

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


一連のサンプルに対して分類子が検証された結果。

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>名前付き項目

### <a name="nmisclassifications--int"></a>N 誤分類: [Int](xref:microsoft.quantum.lang-ref.int)

検証中に観察された誤分類の数。
### <a name="nvalidationsamples--int"></a>NValidationSamples: [Int](xref:microsoft.quantum.lang-ref.int)

