---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854566"
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