---
uid: Microsoft.Quantum.Canon.Compose
title: 関数の作成
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716494"
---
# <a name="compose-function"></a>関数の作成

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


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