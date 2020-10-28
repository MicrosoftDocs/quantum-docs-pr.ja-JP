---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715239"
---
# <a name="uncurriedop-function"></a>UncurriedOp 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


操作を返す関数を指定した場合、は、両方の入力をタプルとして受け取る新しい操作を返します。

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a>入力

### <a name="curriedop--t---u--unit"></a>curriedOp: > ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) 

操作を返す関数。



## <a name="output--tu--unit"></a>出力: (' t, ' U) => [単位](xref:microsoft.quantum.lang-ref.unit) 

と等価の新しい操作 `op` `op(t, u)` `(curriedOp(t))(u)` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

カリー化操作への最初の入力の型。
### <a name="u"></a>' U

カリー化操作への2番目の入力の型。

## <a name="see-also"></a>参照

- [Microsoft. UncurriedOpC](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [Microsoft. UncurriedOpA](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [Microsoft. UncurriedOpCA](xref:Microsoft.Quantum.Canon.UncurriedOpCA)