---
uid: Microsoft.Quantum.Arrays.Chunks
title: チャンク関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221608"
---
# <a name="chunks-function"></a>チャンク関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列を同じ長さの複数の部分に分割します。

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a>入力

### <a name="nelements--int"></a>nElements: [Int](xref:microsoft.quantum.lang-ref.int)

各チャンクの長さ。


### <a name="arr--t"></a>arr: ' t []

分割する配列。



## <a name="output--t"></a>出力: ' t [] []

元の配列の各チャンクを格納している配列。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="remarks"></a>解説

`nElements`がで割り切れない場合、出力の最後の要素はよりも短い場合があることに注意 `Length(arr)` `nElements` してください。