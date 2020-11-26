---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: カラム Nat 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210101"
---
# <a name="columnat-function"></a>カラム Nat 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


マトリックスから列を抽出します。

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>説明

この関数は、行方向の順序で行列内の列を抽出します。
行 corrsponds を最初のインデックスの要素アクセスに抽出すると、それ以上の処理は必要ありません。

## <a name="input"></a>入力

### <a name="column--int"></a>列: [Int](xref:microsoft.quantum.lang-ref.int)

マトリックスの列


### <a name="matrix--t"></a>マトリックス: ' t [] []

2次元行列 (行方向)



## <a name="output--t"></a>出力: ' t []



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

の各要素の型 `matrix` 。

## <a name="see-also"></a>参照

- [Microsoft... 配列. 転置](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft.................](xref:Microsoft.Quantum.Arrays.Diagonal)