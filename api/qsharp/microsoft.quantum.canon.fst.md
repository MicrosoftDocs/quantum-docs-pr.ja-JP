---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840519"
---
# <a name="fst-function"></a>Fst 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ペアが指定されている場合、最初の要素を返します。

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a>入力

### <a name="pair--tu"></a>pair: (' U '、' U)

2つの要素を持つタプル。



## <a name="output--t"></a>出力: t

`pair` の最初の要素。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

ペアの最初のメンバーの型。
### <a name="u"></a>' U

ペアの2番目のメンバーの型。