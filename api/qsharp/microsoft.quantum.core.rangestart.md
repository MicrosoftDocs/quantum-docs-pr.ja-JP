---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713167"
---
# <a name="rangestart-function"></a>RangeStart 関数

名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)

パック [](https://nuget.org/packages/)


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