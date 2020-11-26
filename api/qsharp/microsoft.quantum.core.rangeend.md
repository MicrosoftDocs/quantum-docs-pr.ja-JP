---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 90a9e31bf5c4a5e92a35998ddaec8c9e9de9888e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224039"
---
# <a name="rangeend-function"></a>RangeEnd 関数

名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


指定された範囲の定義済みの終了値を返します。これは必ずしもシーケンスの最後の要素ではありません。

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a>入力

### <a name="range--range"></a>範囲: [範囲](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

指定された範囲の定義済みの終了値。

## <a name="remarks"></a>解説

範囲式の最初の要素は `start` で、2番目の要素は、3番目の要素はなど `start+step` `start+step+step` です。が渡されるまで、が `end` 渡されます。

範囲の定義済みの終了値は、範囲によって指定されたシーケンスの最後の要素と異なる場合があることに注意してください。たとえば、0 ~ の範囲で指定します。 2.. 5最後の要素は4ですが、終了値は5です。