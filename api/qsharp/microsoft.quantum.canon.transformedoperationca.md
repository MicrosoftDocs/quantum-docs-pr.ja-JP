---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 21c9cdfc3b5b266cb3b93e52ee2fa4c655caf795
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715318"
---
# <a name="transformedoperationca-function"></a>TransformedOperationCA 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


関数と操作が指定された場合、指定された関数によって入力が変換される新しい操作を返します。

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a>入力

### <a name="fn--u---t"></a>fn: ' U > ' ではありません

指定された入力を操作によって予期される形式に変換する関数。


### <a name="op--t--unit-adj--ctl"></a>op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl

変換する操作。



## <a name="output--u--unit-adj--ctl"></a>出力: ' U => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl

新しい操作 tbat は、 `fn` 入力を使用してを呼び出し、その結果の出力をに渡し `op` ます。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&


### <a name="u"></a>' U



## <a name="see-also"></a>参照

- [Microsoft. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft...........。](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft... Canon.](xref:Microsoft.Quantum.Canon.Composed)