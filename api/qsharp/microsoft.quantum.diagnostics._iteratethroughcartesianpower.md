---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: _iterateThroughCartesianPower 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: 36666238b40d036e3f6a8949b22f5806216d71f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713139"
---
# <a name="_iteratethroughcartesianpower-operation"></a>_iterateThroughCartesianPower 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


デカルト積を使用して変数を反復処理します [0,、境界 [0]-1] × [0,、境界 [1]-1] × [0,、境界 [長さ (境界)-1]-1]、デカルト積のすべての要素に対して op (arr) を呼び出します。

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a>入力

### <a name="length--int"></a>長さ: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="value--int"></a>値: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--int--unit"></a>op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [単位](xref:microsoft.quantum.lang-ref.unit) 





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

