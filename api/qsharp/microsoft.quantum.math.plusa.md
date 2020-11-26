---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194833"
---
# <a name="plusa-function"></a>PlusA 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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