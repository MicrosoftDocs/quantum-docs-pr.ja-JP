---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: 3529718f0c903266d21fd593c11c0149dae0fa2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220197"
---
# <a name="squarearrayfact-function"></a>SquareArrayFact 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2次元配列に正方形の形状がある条件を表します。

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>説明

この関数は、配列内の各行に、配列内の行 (要素) と同じ数の要素があることをアサートします。

## <a name="input"></a>入力

### <a name="array--t"></a>配列: ' t [] []

2次元の要素の配列。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

配列が正方形配列でない場合に出力されるメッセージ



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

の各要素の型 `array` 。

## <a name="see-also"></a>参照

- [RectangularArrayFact です。](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)