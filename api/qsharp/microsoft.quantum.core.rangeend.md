---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713246"
---
# <a name="rangeend-function"></a>RangeEnd 関数

名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)

パック [](https://nuget.org/packages/)


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