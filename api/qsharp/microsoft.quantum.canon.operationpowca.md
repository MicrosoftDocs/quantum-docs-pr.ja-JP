---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715673"
---
# <a name="operationpowca-function"></a>OperationPowCA 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


操作を累乗します。
修飾子は、 `A` 操作が制御可能であり、adjointable であることを示します。

つまり、ゲート $U $ を表す操作が指定されている場合は、power $m $ に対して ^ m $ $U 新しい操作を返します。

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>入力

### <a name="op--t--unit-ctl--adj"></a>op: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞

繰り返すゲートを表す $ $U 演算。


### <a name="power--int"></a>power: [Int](xref:microsoft.quantum.lang-ref.int)

$U $ を繰り返す回数を指定します。



## <a name="output--t--unit-ctl--adj"></a>出力: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞

$U ^ m $ を表す新しい操作 $m = \texttt{power} $。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

電力を供給する操作の種類。

## <a name="see-also"></a>参照

- [Microsoft...。](xref:Microsoft.Quantum.Canon.OperationPow)