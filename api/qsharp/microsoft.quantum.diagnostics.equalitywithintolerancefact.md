---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712747"
---
# <a name="equalitywithintolerancefact-function"></a>EqualityWithinToleranceFact 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


古典的な浮動小数点値が、指定された絶対許容範囲に最大の予測値を持つことを示す要求を表します。

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a>入力

### <a name="actual--double"></a>実際: [Double](xref:microsoft.quantum.lang-ref.double)

確認する数値。


### <a name="expected--double"></a>が必要です。 [Double](xref:microsoft.quantum.lang-ref.double)

予期される値。


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

実際と予想される差に対する絶対許容値。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

