---
uid: Microsoft.Quantum.Canon.Snd
title: Snd 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205322"
---
# <a name="snd-function"></a>Snd 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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