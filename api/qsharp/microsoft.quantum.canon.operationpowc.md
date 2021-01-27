---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 05b0d5b286e16c308d8c3df8fb8fa1ac8c9868ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852345"
---
# <a name="operationpowc-function"></a>OperationPowC 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


操作を累乗します。
修飾子は、 `C` 操作が制御可能であることを示します。

つまり、ゲート $U $ を表す操作が指定されている場合は、power $m $ に対して ^ m $ $U 新しい操作を返します。

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a>入力

### <a name="op--t--unit--is-ctl"></a>op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です

繰り返すゲートを表す $ $U 演算。


### <a name="power--int"></a>power: [Int](xref:microsoft.quantum.lang-ref.int)

$U $ を繰り返す回数を指定します。



## <a name="output--t--unit--is-ctl"></a>出力: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です

$U ^ m $ を表す新しい操作 $m = \texttt{power} $。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

電力を供給する操作の種類。

## <a name="see-also"></a>参照

- [Microsoft...。](xref:Microsoft.Quantum.Canon.OperationPow)