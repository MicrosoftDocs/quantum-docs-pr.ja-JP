---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 44683b204ecd469f5f5412a7ec06e98ec8a4f37e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224005"
---
# <a name="rangestart-function"></a>RangeStart 関数

名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


指定された範囲の開始値を定義して返します。

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a>入力

### <a name="range--range"></a>範囲: [範囲](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

指定された範囲の開始値。

## <a name="remarks"></a>解説

範囲式の最初の要素は `start` で、2番目の要素は、3番目の要素はなど `start+step` `start+step+step` です。が渡されるまで、が `end` 渡されます。

範囲で空のシーケンスが指定されていない限り、範囲の定義済みの開始値が、シーケンスの最初の要素と同じであることに注意してください (例: 2.. 1)。