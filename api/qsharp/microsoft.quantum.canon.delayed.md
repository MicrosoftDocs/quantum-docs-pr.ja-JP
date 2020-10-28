---
uid: Microsoft.Quantum.Canon.Delayed
title: 遅延関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716256"
---
# <a name="delayed-function"></a>遅延関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


指定された引数を使用して指定された操作を適用する操作を返します。

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a>入力

### <a name="op--t--u"></a>op: t => ' U 

適用する操作。


### <a name="arg--t"></a>arg: ' t '

操作が適用される入力。



## <a name="output--unit--u"></a>出力: [Unit](xref:microsoft.quantum.lang-ref.unit) => ' U 

入力と共に適用される新しい操作 `op``arg`

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

遅延する操作の入力型。
### <a name="u"></a>' U

遅延する操作の戻り値の型。

## <a name="see-also"></a>参照

- [Microsoft.. Canon. DelayedC](xref:Microsoft.Quantum.Canon.DelayedC)
- [Microsoft.. Canon. DelayedA](xref:Microsoft.Quantum.Canon.DelayedA)
- [Microsoft.. Canon. DelayedCA](xref:Microsoft.Quantum.Canon.DelayedCA)
- [Microsoft. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)