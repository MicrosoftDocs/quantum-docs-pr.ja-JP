---
uid: Microsoft.Quantum.Arrays.ElementAt
title: ElementAt 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementAt
qsharp.summary: Returns the at the given index of an array.
ms.openlocfilehash: 2d31c62a4a5ba3b273e7440b5dfe4482b47e3a8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842816"
---
# <a name="elementat-function"></a>ElementAt 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列の指定したインデックス位置にあるを返します。

```qsharp
function ElementAt<'T> (index : Int, array : 'T[]) : 'T
```


## <a name="input"></a>入力

### <a name="index--int"></a>index: [Int](xref:microsoft.quantum.lang-ref.int)

要素のインデックス


### <a name="array--t"></a>配列: ' t []

インデックスが作成される配列。



## <a name="output--t"></a>出力: t



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

の各要素の型 `array` 。

## <a name="example"></a>例

4つの有名な整数シーケンスの3番目の数値を取得します。 (0 のインデックスは、シーケンスの _最初_ の値に対応していることに注意してください)。

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famous2 = Mapped(ElementAt<Int>(2, _), [lucas, prime, fibonacci, catalan]);
// same as: famous2 = [3, 5, 1, 2]
```

## <a name="see-also"></a>参照

- [Microsoft. Quantum. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)
- [Microsoft... Arrays. ElementsAt](xref:Microsoft.Quantum.Arrays.ElementsAt)