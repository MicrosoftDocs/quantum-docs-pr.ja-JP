---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 1e54a5a086035f5f8d36d777badb306156d99600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720427"
---
# <a name="validationresults-user-defined-type"></a>ValidationResults ユーザー定義型

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パック [](https://nuget.org/packages/)


一連のサンプルに対して分類子が検証された結果。

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>名前付き項目

### <a name="nmisclassifications--int"></a>N 誤分類: [Int](xref:microsoft.quantum.lang-ref.int)

検証中に観察された誤分類の数。
### <a name="nvalidationsamples--int"></a>NValidationSamples: [Int](xref:microsoft.quantum.lang-ref.int)

