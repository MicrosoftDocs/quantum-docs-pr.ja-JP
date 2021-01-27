---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850982"
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

## <a name="example"></a>例

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a>解説

との差は、 `from` `to` 値に適合する必要があり `Int` ます。