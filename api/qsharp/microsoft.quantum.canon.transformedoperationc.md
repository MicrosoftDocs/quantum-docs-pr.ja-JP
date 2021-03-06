---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: TransformedOperationC 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9475c5a1cc3b7e14c56c301749311a72e15f71e0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852040"
---
# <a name="transformedoperationc-function"></a>TransformedOperationC 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


関数と操作が指定された場合、指定された関数によって入力が変換される新しい操作を返します。

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a>入力

### <a name="fn--u---t"></a>fn: ' U > ' ではありません

指定された入力を操作によって予期される形式に変換する関数。


### <a name="op--t--unit--is-ctl"></a>op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です

変換する操作。



## <a name="output--u--unit--is-ctl"></a>出力: ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です

新しい操作 tbat は、 `fn` 入力を使用してを呼び出し、その結果の出力をに渡し `op` ます。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&


### <a name="u"></a>' U



## <a name="example"></a>例

次の呼び出しでは、を使用して、入力用に設計された操作を、 @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" @"Microsoft.Quantum.Arithmetic.BigEndian" 型の入力を受け入れる操作に変換し @"Microsoft.Quantum.Arithmetic.LittleEndian" ます。

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a>参照

- [Microsoft. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft...........。](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft... Canon.](xref:Microsoft.Quantum.Canon.Composed)