---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724324"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult ユーザー定義型

名前空間: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

パック [](https://nuget.org/packages/)


Uni可変 ate 関数を最適化した結果を表します。

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>名前付き項目

### <a name="coordinate--double"></a>座標: [Double](xref:microsoft.quantum.lang-ref.double)

最適なが見つかった入力。
### <a name="value--double"></a>値: [Double](xref:microsoft.quantum.lang-ref.double)

関数によって最適な値が返されます。