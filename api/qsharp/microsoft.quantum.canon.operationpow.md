---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 9ed0d32c084f183527cac0586ad699417f51df29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852376"
---
# <a name="operationpow-function"></a>OperationPow 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


操作を累乗します。

つまり、ゲート $U $ を表す操作が指定されている場合は、power $m $ に対して ^ m $ $U 新しい操作を返します。

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a>入力

### <a name="op--t--unit"></a>op: t => [単位](xref:microsoft.quantum.lang-ref.unit) 

繰り返すゲートを表す $ $U 演算。


### <a name="power--int"></a>power: [Int](xref:microsoft.quantum.lang-ref.int)

$U $ を繰り返す回数を指定します。



## <a name="output--t--unit"></a>出力: t => [Unit](xref:microsoft.quantum.lang-ref.unit) 

$U ^ m $ を表す新しい操作 $m = \texttt{power} $。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

電力を供給する操作の種類。

## <a name="see-also"></a>参照

- [Microsoft. OperationPowC](xref:Microsoft.Quantum.Canon.OperationPowC)
- [Microsoft. OperationPowA](xref:Microsoft.Quantum.Canon.OperationPowA)
- [Microsoft. OperationPowCA](xref:Microsoft.Quantum.Canon.OperationPowCA)