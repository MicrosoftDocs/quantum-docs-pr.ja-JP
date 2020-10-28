---
uid: Microsoft.Quantum.Optimization.Probe
title: Probe 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: Probe
qsharp.summary: Given an interval, returns a probe interval that contracts the given interval by a factor of the golden ratio.
ms.openlocfilehash: 664d1f0337aa0285e95c78d313b5aaed89b62794
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724987"
---
# <a name="probe-function"></a>Probe 関数

名前空間: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

パック [](https://nuget.org/packages/)


間隔を指定すると、指定された期間をゴールデン比率の係数でコントラクトするプローブ間隔を返します。

```qsharp
function Probe (left : Double, right : Double) : (Double, Double)
```


## <a name="input"></a>入力

### <a name="left--double"></a>left: [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="right--double"></a>right: [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--doubledouble"></a>出力: ([double](xref:microsoft.quantum.lang-ref.double)、[double](xref:microsoft.quantum.lang-ref.double))

