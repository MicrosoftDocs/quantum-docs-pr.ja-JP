---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713363"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray 関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パック [](https://nuget.org/packages/)


Start. で列挙された整数の配列を作成します `arr` 。ステップ..終わり。

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>入力

### <a name="range--range"></a>範囲: [範囲](xref:microsoft.quantum.lang-ref.range)

`Range` `start..step..end` 配列に変換する値の。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)[]

によって反復処理される値に対応する整数の新しい配列 `range` 。