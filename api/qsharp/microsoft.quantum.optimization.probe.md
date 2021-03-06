---
uid: Microsoft.Quantum.Optimization.Probe
title: Probe 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: Probe
qsharp.summary: Given an interval, returns a probe interval that contracts the given interval by a factor of the golden ratio.
ms.openlocfilehash: 18904f8b7496b62d51ddd72bd32ccc33518266e8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842663"
---
# <a name="probe-function"></a>Probe 関数

名前空間: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


間隔を指定すると、指定された期間をゴールデン比率の係数でコントラクトするプローブ間隔を返します。

```qsharp
function Probe (left : Double, right : Double) : (Double, Double)
```


## <a name="input"></a>入力

### <a name="left--double"></a>left: [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="right--double"></a>right: [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--doubledouble"></a>出力: ([double](xref:microsoft.quantum.lang-ref.double)、[double](xref:microsoft.quantum.lang-ref.double))

