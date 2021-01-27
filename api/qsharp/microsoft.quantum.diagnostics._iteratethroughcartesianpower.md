---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: _iterateThroughCartesianPower 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: a27302be75ee701b0629310700b56d222aaef7db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853573"
---
# <a name="_iteratethroughcartesianpower-operation"></a>_iterateThroughCartesianPower 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


デカルト積を使用して変数を反復処理します [0,、境界 [0]-1] × [0,、境界 [1]-1] × [0,、境界 [長さ (境界)-1]-1]、デカルト積のすべての要素に対して op (arr) を呼び出します。

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a>入力

### <a name="length--int"></a>長さ: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="value--int"></a>値: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--int--unit"></a>op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [単位](xref:microsoft.quantum.lang-ref.unit) 





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

