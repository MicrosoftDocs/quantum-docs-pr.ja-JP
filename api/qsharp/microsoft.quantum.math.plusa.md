---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709606"
---
# <a name="plusa-function"></a>PlusA 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パック [](https://nuget.org/packages/)


2つの入力の合計 (連結) を返します。

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a>入力

### <a name="a--element"></a>a: ' Element []

合計する $ $a 最初の入力。


### <a name="b--element"></a>b: ' Element []

合計する $ $b 2 番目の入力。



## <a name="output--element"></a>出力: ' Element []

合計 $a + b $ です。

## <a name="type-parameters"></a>型パラメーター

### <a name="element"></a>' 要素

2つの入力配列のそれぞれに含まれる各要素の型。