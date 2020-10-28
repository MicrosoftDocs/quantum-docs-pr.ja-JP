---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715220"
---
# <a name="uncurriedopa-function"></a>UncurriedOpA 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


操作を返す関数を指定した場合、は、両方の入力をタプルとして受け取る新しい操作を返します。
修飾子は、 `A` 操作が adjointable であることを示します。

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a>入力

### <a name="curriedop--t---u--unit-adj"></a>curriedOp: > ' U => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

操作を返す関数。



## <a name="output--tu--unit-adj"></a>出力: (' t, ' U) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

と等価の新しい操作 `op` `op(t, u)` `(curriedOp(t))(u)` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

カリー化関数の1番目の引数の型。
### <a name="u"></a>' U

カリー化関数の2番目の引数の型。

## <a name="see-also"></a>参照

- [Microsoft... Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)