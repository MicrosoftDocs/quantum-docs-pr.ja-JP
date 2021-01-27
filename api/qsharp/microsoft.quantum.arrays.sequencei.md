---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3cf09e48cce1aeb1aac837465ee3a5e06adf5169
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851003"
---
# <a name="sequencei-function"></a>SequenceI 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された間隔で整数の配列を取得します。

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a>入力

### <a name="from--int"></a>開始: [Int](xref:microsoft.quantum.lang-ref.int)

間隔の包括開始インデックス。


### <a name="to--int"></a>to: [Int](xref:microsoft.quantum.lang-ref.int)

より小さくない間隔の包括終了インデックス `from` 。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)[]

数値のシーケンス ( `from` `from + 1` ,...) を `to` 格納している配列。

## <a name="example"></a>例

```qsharp
let arr1 = SequenceI(0, 3); // [0, 1, 2, 3]
let arr2 = SequenceI(23, 29); // [23, 24, 25, 26, 27, 28, 29]
let arr3 = SequenceI(-5, -2); // [-5, -4, -3, -2]

let numbers = SequenceI(0, _); // function to create sequence from 0 to `to`
let naturals = SequenceI(1, _); // function to create sequence from 1 to `to`
```