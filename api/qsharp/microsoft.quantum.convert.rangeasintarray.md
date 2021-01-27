---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850101"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray 関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Start. で列挙された整数の配列を作成します `arr` 。ステップ..終わり。

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>入力

### <a name="range--range"></a>範囲: [範囲](xref:microsoft.quantum.lang-ref.range)

`Range` `start..step..end` 配列に変換する値の。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)[]

によって反復処理される値に対応する整数の新しい配列 `range` 。

## <a name="example"></a>例

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```