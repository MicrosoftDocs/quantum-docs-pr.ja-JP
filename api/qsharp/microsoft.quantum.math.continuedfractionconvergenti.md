---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentI
title: ContinuedFractionConvergentI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentI
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: c5316c13ce499da88c0d5c45b9d8c5e3a8c6162d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853854"
---
# <a name="continuedfractionconvergenti-function"></a>ContinuedFractionConvergentI 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


に最も近い `fraction` 、分母が以下である継続分数の値を検索します。 `denominatorBound`

```qsharp
function ContinuedFractionConvergentI (fraction : Microsoft.Quantum.Math.Fraction, denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a>入力

### <a name="fraction--fraction"></a>分数: [分数](xref:Microsoft.Quantum.Math.Fraction)




### <a name="denominatorbound--int"></a>denominatorBound: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--fraction"></a>出力: [分数](xref:Microsoft.Quantum.Math.Fraction)

分母が以下の場合に最も近い継続分数 `fraction``denominatorBound`