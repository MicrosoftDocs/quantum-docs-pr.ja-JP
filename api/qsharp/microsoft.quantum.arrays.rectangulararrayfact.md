---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718922"
---
# <a name="rectangulararrayfact-function"></a>RectangularArrayFact 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


2次元配列に四角形の形状がある条件を表します。

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>説明

この関数は、配列内の各行の長さが同じであることをアサートします。

## <a name="input"></a>入力

### <a name="array--t"></a>配列: ' t [] []

2次元の要素の配列。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

配列が四角形の配列でない場合に印刷されるメッセージ



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

の各要素の型 `array` 。

## <a name="see-also"></a>参照

- [SquareArrayFact です。](xref:Microsoft.Quantum.Arrays.SquareArrayFact)