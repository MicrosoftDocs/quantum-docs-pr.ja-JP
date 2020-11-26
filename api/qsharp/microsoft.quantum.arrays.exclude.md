---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 4ea0d754fce4fc7e3e4e42e55b56720cb3f95ca6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221353"
---
# <a name="exclude-function"></a>Exclude 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定されたインデックスリストの要素を除く、別の配列の要素を含む配列を返します。

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>入力

### <a name="remove--int"></a>削除: [Int](xref:microsoft.quantum.lang-ref.int)[]

出力から除外する要素を示すインデックスの配列。


### <a name="array--t"></a>配列: ' t []

出力配列内の値を取得する対象の配列。



## <a name="output--t"></a>出力: ' t []

インデックスが `output` `output[0]` `array` に表示されない `remove` 、2番目の要素などのの最初の要素である配列 `output[1]` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

配列要素の型。