---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: 4d8596c52b0fc8082a2b766d95d4052a4964b8b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197586"
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