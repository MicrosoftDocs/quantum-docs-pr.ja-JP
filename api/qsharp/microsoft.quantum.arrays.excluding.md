---
uid: Microsoft.Quantum.Arrays.Excluding
title: 除外 (関数を)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 8848c6e89da50efb4f7550168f1757b25a214a24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719275"
---
# <a name="excluding-function"></a>除外 (関数を)

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


指定されたインデックスリストの要素を除く、別の配列の要素を含む配列を返します。

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
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