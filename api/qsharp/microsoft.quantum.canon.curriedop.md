---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: f811347d65a6460690163e9df631979c906bd89f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840765"
---
# <a name="curriedop-function"></a>CurriedOp 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2つの入力に対して、カリー化された操作のバージョンを返します。

つまり、2つの入力を持つ演算が指定された場合、この関数は、isomorphism $f (x, y) \equiv f (x) (y) $ という値を適用して、1つの入力の操作を返す1つの入力の操作を返します。

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a>入力

### <a name="op--tu--unit"></a>op: (' U) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

入力がペアである操作。



## <a name="output--t---u--unit"></a>出力: > ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) 

ペアの最初の要素を受け取り、元の操作の入力の2番目の要素を入力として受け入れる演算を返す操作。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

ペアで定義された関数の最初のコンポーネントの型。
### <a name="u"></a>' U

ペアで定義された関数の2番目のコンポーネントの型。

## <a name="remarks"></a>解説

同等のものを次に示します。

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```