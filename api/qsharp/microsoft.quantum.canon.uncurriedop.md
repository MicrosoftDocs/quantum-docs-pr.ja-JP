---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: d707b52bb17f4dea795fa4ff824c785e506b8b20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852006"
---
# <a name="uncurriedop-function"></a>UncurriedOp 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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