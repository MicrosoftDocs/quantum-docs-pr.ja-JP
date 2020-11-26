---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: c23d85cf513bb6d37e67260eeeb3b81b42e6771a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198029"
---
# <a name="greaterthand-function"></a>GreaterThanD 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


数値が別の数値より大きい場合にのみ true を返します。

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a>入力

### <a name="a--double"></a>a: [Double](xref:microsoft.quantum.lang-ref.double)

比較する最初の値。


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

比較する2番目の値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true``a`が厳密により大きい場合にのみ `b` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```