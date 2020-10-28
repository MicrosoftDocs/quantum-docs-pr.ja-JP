---
uid: Microsoft.Quantum.Canon.Delay
title: 遅延操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716317"
---
# <a name="delay-operation"></a>遅延操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


指定された操作を遅延付きで適用します。

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a>説明

操作とその操作への入力を指定した場合、追加の入力が提供されると、によって操作が適用されます。
特に、式 `Delay(op, arg, _)` は、 `op` 呼び出されたときにに適用される演算です `arg` 。
式 `Delay(op,arg,_)` を使用すると、のアプリケーションを遅延させることができ `op` ます。

## <a name="input"></a>入力

### <a name="op--t--u"></a>op: t => ' U 

適用する操作。


### <a name="arg--t"></a>arg: ' t '

操作が適用される入力。


### <a name="aux--unit"></a>aux: [ユニット](xref:microsoft.quantum.lang-ref.unit)

部分アプリケーションを使用して操作のアプリケーションを遅延させるために使用される引数。



## <a name="output--u"></a>出力: ' U



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

遅延する操作の入力型。
### <a name="u"></a>' U

遅延する操作の戻り値の型。

## <a name="see-also"></a>参照

- [Microsoft.. Canon. DelayC](xref:Microsoft.Quantum.Canon.DelayC)
- [Microsoft の Quantum... DelayA](xref:Microsoft.Quantum.Canon.DelayA)
- [Microsoft. Canon. DelayCA](xref:Microsoft.Quantum.Canon.DelayCA)
- [Microsoft.........](xref:Microsoft.Quantum.Canon.Delayed)