---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 45526c0202e417213aab3fe7819827588e794e23
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216389"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


操作を返す関数を指定した場合、は、両方の入力をタプルとして受け取る新しい操作を返します。
修飾子は、 `CA` 操作が制御可能であり、adjointable であることを示します。

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>入力

### <a name="curriedop--t---u--unit--is-adj--ctl"></a>curriedOp: > ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

操作を返す関数。



## <a name="output--tu--unit--is-adj--ctl"></a>出力: (' t, ' U) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

と等価の新しい操作 `op` `op(t, u)` `(curriedOp(t))(u)` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

カリー化関数の1番目の引数の型。
### <a name="u"></a>' U

カリー化関数の2番目の引数の型。

## <a name="see-also"></a>参照

- [Microsoft... Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)