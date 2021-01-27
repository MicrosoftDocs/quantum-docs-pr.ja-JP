---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842192"
---
# <a name="windows-function"></a>Windows 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


長さの連続するすべてのサブを返し `size` ます。

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>説明

この関数 `n - size + 1` は、すべての長さのサブを返し `size` ます。ここで、 `n` はの長さ `arr` です。
最初のサブは、最後のサブ `arr[0..size - 1], arr[1..size], arr[2..size + 1]` 配列まで `arr[n - size..n - 1]` です。

`size <= 0`または `size > n` の場合は、空の配列が返されます。

## <a name="input"></a>入力

### <a name="size--int"></a>サイズ: [Int](xref:microsoft.quantum.lang-ref.int)

サブの長さ。


### <a name="array--t"></a>配列: ' t []

要素の配列。



## <a name="output--t"></a>出力: ' t [] []



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

要素の型 `array` 。

## <a name="example"></a>例

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```