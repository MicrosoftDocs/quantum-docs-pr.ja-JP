---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202925"
---
# <a name="sizeadjustedtruthtable-function"></a>SizeAdjustedTruthTable 関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


変数の数に基づいてブール値の配列から真理値テーブルを調整します

新しい配列が長さとして返され `2^numVars` ます。これは、 `table` エントリのサイズを拡張したり、要素に切り捨てたりすることが必要になる可能性が `false` `2^numVars` あります。

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a>入力

### <a name="table--bool"></a>テーブル: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

真理値の配列としての真理値テーブル


### <a name="numvars--int"></a>numVars: [Int](xref:microsoft.quantum.lang-ref.int)

変数の数



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

サイズ調整された真理値テーブル