---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194034"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult ユーザー定義型

名前空間: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Uni可変 ate 関数を最適化した結果を表します。

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>名前付き項目

### <a name="coordinate--double"></a>座標: [Double](xref:microsoft.quantum.lang-ref.double)

最適なが見つかった入力。
### <a name="value--double"></a>値: [Double](xref:microsoft.quantum.lang-ref.double)

関数によって最適な値が返されます。