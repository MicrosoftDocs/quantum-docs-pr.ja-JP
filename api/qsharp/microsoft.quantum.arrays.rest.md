---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718915"
---
# <a name="rest-function"></a>Rest 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


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