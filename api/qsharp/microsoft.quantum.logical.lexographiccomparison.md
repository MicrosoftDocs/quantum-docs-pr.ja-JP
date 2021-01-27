---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: de8179ab6e835d08e7f41287f31a876b7ecc91c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814382"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


比較関数を指定した場合は、lexographically が2つの配列を比較する新しい関数を返します。

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a>入力

### <a name="elementcomparison--tt---bool"></a>elementComparison: (' t, ' t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)

との2つの要素を比較し、 `x` `y` が以下の場合にを返す関数 `x` `y` 。



## <a name="output--tt---bool"></a>出力: (' t [], ' t [])-> [Bool](xref:microsoft.quantum.lang-ref.bool)

との2つの配列を比較 `xs` `ys` し、 `xs` `ys` lexographical 順序でのの前後にが発生した場合にを返す関数。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

比較対象の配列の要素の型。

## <a name="remarks"></a>解説

2つの配列間の lexographic 比較 `xs` `ys` は、次の手順で定義します。 とは2つの要素であり `x` `y` `elementComparison(x, y)` 、との `elementComparison(y, x)` 両方が true の場合は等価です。

- 両方の配列は、等価でない要素の最初のペアまで、要素ごとに比較されます。 に従って最初に発生する要素を含む配列 `elementComparison` は、lexographical の順序で最初に発生すると言います。
- 等価でない要素が見つからず、一方の配列が他方よりも長い場合、短い方の配列が最初に出現すると言われます。

## <a name="see-also"></a>参照

- [Microsoft... array. Sorted](xref:Microsoft.Quantum.Arrays.Sorted)