---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715771"
---
# <a name="operationpow-function"></a>OperationPow 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


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