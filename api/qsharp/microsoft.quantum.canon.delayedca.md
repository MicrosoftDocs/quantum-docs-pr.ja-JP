---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716219"
---
# <a name="delayedca-function"></a>DelayedCA 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


指定された引数を使用して指定された操作を適用する操作を返します。

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a>入力

### <a name="op--t--unit-ctl--adj"></a>op: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞

戻り値を適用した結果として適用される操作


### <a name="arg--t"></a>arg: ' t '

操作が適用される入力 `op` 。



## <a name="output--unit--unit-ctl--adj"></a>出力: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞

入力と共に適用される新しい操作 `op``arg`

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

遅延する操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft.........](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)