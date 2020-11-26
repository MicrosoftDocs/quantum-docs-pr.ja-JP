---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220010"
---
# <a name="unique-function"></a>Unique 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


隣接する要素が等しくない新しい配列を返します。

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>説明

要素の配列と関数が等しいかどうかをテストするために、この関数は要素の相対順序を保持する新しい配列を返しますが、等しいすべての隣接する要素は、1つの要素だけにフィルター処理されます。

## <a name="input"></a>入力

### <a name="equal--tt---bool"></a>equal: (t, t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)

`a` `b` がである場合にと等しいと見なされる2つの要素を比較する関数 `equal(a, b)` `true` 。


### <a name="array--t"></a>配列: ' t []

一意の要素をフィルター処理する対象の配列。



## <a name="output--t"></a>出力: ' t []

隣接する要素が等しくない配列。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

の各要素の型 `array` 。

## <a name="remarks"></a>解説

等しいが、互いに隣接していない複数の要素がある場合は、出力配列に複数の要素が出現します。  この関数をと共に使用して `Sorted` 、一意の要素全体を含む配列を取得します。