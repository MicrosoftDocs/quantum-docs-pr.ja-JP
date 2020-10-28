---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716186"
---
# <a name="fst-function"></a>Fst 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


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