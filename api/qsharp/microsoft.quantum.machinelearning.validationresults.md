---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 923fd80333b6bf77daeaac2bf205db620e61cfd0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846091"
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

