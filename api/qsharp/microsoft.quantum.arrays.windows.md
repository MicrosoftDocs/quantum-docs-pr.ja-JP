---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718747"
---
# <a name="windows-function"></a>Windows 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


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