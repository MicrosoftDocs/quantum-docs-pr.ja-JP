---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: b2c5f11c0d92ddf9214de2d439c175319c569be0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220835"
---
# <a name="issorted-function"></a>IsSorted 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列が指定されている場合、指定された比較関数によって定義されたとおりに配列が並べ替えられるかどうかを返します。

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>入力

### <a name="comparison--tt---bool"></a>比較: (' t, ' t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)

`a` `b` がの場合に、以下の2つの要素を比較する関数 `comparison(a, b)` `true` 。


### <a name="array--t"></a>配列: ' t []

チェックする配列。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 要素の各ペアと、その順序で発生する場合にのみ `a` `b` `array` 、 `comparison(a, b)` はに `true` なります。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

の各要素の型 `array` 。

## <a name="remarks"></a>解説

関数は `comparison` 推移的であると見なされ、 `comparison(a, b)` との場合はと `comparison(b, c)` 見なされ `comparison(a, c)` ます。 このプロパティがを保持していない場合、この関数の出力は正しくない可能性があります。