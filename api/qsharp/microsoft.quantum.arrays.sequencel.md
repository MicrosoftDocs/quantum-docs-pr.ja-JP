---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220265"
---
# <a name="sequencel-function"></a>SequenceL 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された間隔で整数の配列を取得します。

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>入力

### <a name="from--bigint"></a>開始: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

間隔の包括開始インデックス。


### <a name="to--bigint"></a>to: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

より小さくない間隔の包括終了インデックス `from` 。



## <a name="output--bigint"></a>出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]

数値のシーケンス ( `from` `from + 1` ,...) を `to` 格納している配列。

## <a name="remarks"></a>解説

との差は、 `from` `to` 値に適合する必要があり `Int` ます。