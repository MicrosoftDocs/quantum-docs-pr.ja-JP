---
uid: Microsoft.Quantum.Canon.Snd
title: Snd 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: 11786fa195de12a7f2e4f2edb00ac0bc1071dd5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852155"
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