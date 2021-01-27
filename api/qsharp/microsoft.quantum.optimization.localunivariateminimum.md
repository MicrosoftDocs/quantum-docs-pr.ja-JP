---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854606"
---
# <a name="localunivariateminimum-function"></a>LocalUnivariateMinimum 関数

名前空間: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ゴールデン interval 検索を使用して、範囲指定された期間にわたって、uni可変 ate 関数のローカル最小値を返します。

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a>入力

### <a name="fn--double---double"></a>fn: [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)

最小化される uniバリエーション関数。


### <a name="bounds--doubledouble"></a>境界: ([double](xref:microsoft.quantum.lang-ref.double)、[double](xref:microsoft.quantum.lang-ref.double))

ローカル最小値が検索される間隔。


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

許容される関数入力の精度。
ローカル最適化 a の検索は、間隔がこの許容範囲を下回るまで続行されます。



## <a name="output--univariateoptimizationresult"></a>出力: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)

指定された範囲内にある、指定された関数のローカル最適化 a。