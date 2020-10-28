---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 349424a102dba7354bbaa65fffdc2b5d506a3b91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715332"
---
# <a name="transformedoperationa-function"></a>TransformedOperationA 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


関数と操作が指定された場合、指定された関数によって入力が変換される新しい操作を返します。

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a>入力

### <a name="fn--u---t"></a>fn: ' U > ' ではありません

指定された入力を操作によって予期される形式に変換する関数。


### <a name="op--t--unit-adj"></a>op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

変換する操作。



## <a name="output--u--unit-adj"></a>出力: ' U => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

新しい操作 tbat は、 `fn` 入力を使用してを呼び出し、その結果の出力をに渡し `op` ます。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&


### <a name="u"></a>' U



## <a name="see-also"></a>参照

- [Microsoft. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. TransformedOperationC](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [Microsoft. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft...........。](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft... Canon.](xref:Microsoft.Quantum.Canon.Composed)