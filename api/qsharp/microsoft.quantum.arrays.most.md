---
uid: Microsoft.Quantum.Arrays.Most
title: ほとんどの関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 81e66e0b64ae8dfc44d163b68370ccadd191c729
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220605"
---
# <a name="most-function"></a>ほとんどの関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


最後の配列要素が削除される点を除いて、入力配列と等しい配列を作成します。

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>入力

### <a name="array--t"></a>配列: ' t []

最初から2番目の要素が出力配列を形成する配列。



## <a name="output--t"></a>出力: ' t []

要素を格納している配列 `array[0..Length(array) - 2]` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

配列要素の型。