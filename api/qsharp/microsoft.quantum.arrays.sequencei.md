---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718898"
---
# <a name="sequencei-function"></a>SequenceI 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


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