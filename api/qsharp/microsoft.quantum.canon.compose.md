---
uid: Microsoft.Quantum.Canon.Compose
title: 関数の作成
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840902"
---
# <a name="compose-function"></a>関数の作成

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2つの関数の合成を返します。

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>説明

$ および $g $ $f 2 つの関数が指定されている場合、$f-circ g $ を表す新しい関数を返します。

## <a name="input"></a>入力

### <a name="outer--u---v"></a>外部: ' U-> ' V

適用する2番目の関数。


### <a name="inner--t---u"></a>内部: > ' U

適用される最初の関数。



## <a name="output--t---v"></a>出力: > ' V

$、$F (g (x)) = h (x) $ のすべての入力 $x の新しい関数 $h $。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

適用する最初の関数の入力型。
### <a name="u"></a>' U

適用される最初の関数の出力型と、適用する2番目の関数の入力型。
### <a name="v"></a>' V

適用する2番目の関数の出力型。