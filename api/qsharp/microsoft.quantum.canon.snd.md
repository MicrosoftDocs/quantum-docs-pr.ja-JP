---
uid: Microsoft.Quantum.Canon.Snd
title: Snd 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715449"
---
# <a name="snd-function"></a>Snd 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


ペアが指定されると、はその2番目の要素を返します。

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a>入力

### <a name="pair--tu"></a>pair: (' U '、' U)

2つの要素を持つタプル。



## <a name="output--u"></a>出力: ' U

の2番目の要素 `pair` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

ペアの最初のメンバーの型。
### <a name="u"></a>' U

ペアの2番目のメンバーの型。