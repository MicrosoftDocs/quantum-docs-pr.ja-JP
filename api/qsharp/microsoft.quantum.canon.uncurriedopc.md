---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715211"
---
# <a name="uncurriedopc-function"></a>UncurriedOpC 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


操作を返す関数を指定した場合、は、両方の入力をタプルとして受け取る新しい操作を返します。
修飾子は、 `C` 操作が制御可能であることを示します。

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>入力

### <a name="curriedop--t---u--unit-ctl"></a>curriedOp: > ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

操作を返す関数。



## <a name="output--tu--unit-ctl"></a>出力: (' U '、' U) => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl

と等価の新しい操作 `op` `op(t, u)` `(curriedOp(t))(u)` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

カリー化関数の1番目の引数の型。
### <a name="u"></a>' U

カリー化関数の2番目の引数の型。

## <a name="see-also"></a>参照

- [Microsoft... Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)