---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: c44e3448c471f2a20f995d4546ee54f3affb726e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840546"
---
# <a name="delayedca-function"></a>DelayedCA 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された引数を使用して指定された操作を適用する操作を返します。

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a>入力

### <a name="op--t--unit--is-adj--ctl"></a>op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

戻り値を適用した結果として適用される操作


### <a name="arg--t"></a>arg: ' t '

操作が適用される入力 `op` 。



## <a name="output--unit--unit--is-adj--ctl"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

入力と共に適用される新しい操作 `op``arg`

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

遅延する操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft.........](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)