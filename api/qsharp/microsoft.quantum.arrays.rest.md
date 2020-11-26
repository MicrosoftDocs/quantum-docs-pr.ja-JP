---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: 4dd10b6e8839fd906ca9c2e36c89c626d5772149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220394"
---
# <a name="rest-function"></a>Rest 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


最初の配列要素が削除される点を除いて、入力配列と等しい配列を作成します。

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>入力

### <a name="array--t"></a>配列: ' t []

最後の要素が出力配列を形成する配列。



## <a name="output--t"></a>出力: ' t []

要素を格納している配列 `array[1..Length(array) - 1]` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

配列要素の型。