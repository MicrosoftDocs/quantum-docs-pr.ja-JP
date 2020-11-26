---
uid: Microsoft.Quantum.Canon.DelayCA
title: DelayCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: a32a4f4a3f5d0f253a4c4eaf28c67db8da978b0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207090"
---
# <a name="delayca-operation"></a>DelayCA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された操作を遅延付きで適用します。

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

操作とその操作への入力を指定した場合、追加の入力が提供されると、によって操作が適用されます。
特に、式 `Delay(op, arg, _)` は、 `op` 呼び出されたときにに適用される演算です `arg` 。
式 `Delay(op,arg,_)` を使用すると、のアプリケーションを遅延させることができ `op` ます。

## <a name="input"></a>入力

### <a name="op--t--unit--is-adj--ctl"></a>op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

適用する操作。


### <a name="arg--t"></a>arg: ' t '

操作が適用される入力。


### <a name="aux--unit"></a>aux: [ユニット](xref:microsoft.quantum.lang-ref.unit)

部分アプリケーションを使用して操作のアプリケーションを遅延させるために使用される引数。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

遅延する操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)
- [Microsoft.........](xref:Microsoft.Quantum.Canon.Delayed)