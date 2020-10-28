---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716214"
---
# <a name="delayedc-function"></a>DelayedC 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


指定された引数を使用して指定された操作を適用する操作を返します。

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>入力

### <a name="op--t--unit-ctl"></a>op: ' t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl

戻り値を適用した結果として適用される操作


### <a name="arg--t"></a>arg: ' t '

操作が適用される入力 `op` 。



## <a name="output--unit--unit-ctl"></a>出力: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl

入力と共に適用される新しい操作 `op``arg`

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

遅延する操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft.........](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)