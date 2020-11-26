---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213839"
---
# <a name="rangereverse-function"></a>RangeReverse 関数

名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


入力範囲の逆の新しい範囲を返します。

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a>入力

### <a name="r--range"></a>r: [範囲](xref:microsoft.quantum.lang-ref.range)

入力範囲。



## <a name="output--range"></a>出力: [範囲](xref:microsoft.quantum.lang-ref.range)

指定された範囲の逆の新しい範囲。

## <a name="remarks"></a>解説

範囲の最後の要素はと同じでない可能性があるため、範囲の反転は単に.. `end` `-step` .. `start` ではないことに注意 `end` してください。