---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: d8c2f52290ce89d0a8ff138ba25f6b2e5e0516d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715337"
---
# <a name="transformedoperation-function"></a>TransformedOperation 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


関数と操作が指定された場合、指定された関数によって入力が変換される新しい操作を返します。

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a>入力

### <a name="fn--u---t"></a>fn: ' U > ' ではありません

指定された入力を操作によって予期される形式に変換する関数。


### <a name="op--t--unit"></a>op: t => [単位](xref:microsoft.quantum.lang-ref.unit) 

変換する操作。



## <a name="output--u--unit"></a>出力: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) 

新しい操作 tbat は、 `fn` 入力を使用してを呼び出し、その結果の出力をに渡し `op` ます。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&


### <a name="u"></a>' U



## <a name="see-also"></a>参照

- [Microsoft. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. TransformedOperationC](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [Microsoft. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft...........。](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft... Canon.](xref:Microsoft.Quantum.Canon.Composed)