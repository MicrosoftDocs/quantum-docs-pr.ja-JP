---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718879"
---
# <a name="sequencel-function"></a>SequenceL 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


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