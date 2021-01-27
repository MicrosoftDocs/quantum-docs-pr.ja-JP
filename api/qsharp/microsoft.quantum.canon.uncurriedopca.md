---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 910d8a3006a2f217888b791e479e10f9f1a6965e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840036"
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