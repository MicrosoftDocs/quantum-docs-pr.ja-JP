---
uid: Microsoft.Quantum.Logical.EqualR
title: EqualR 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710031"
---
# <a name="equalr-function"></a>EqualR 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パック [](https://nuget.org/packages/)


2つの入力が等しい場合にのみ true を返します。

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>入力

### <a name="a--__invalidresult__"></a>a: __無効 <Result>__

比較する最初の値。


### <a name="b--__invalidresult__"></a>b: __無効 <Result>__

比較する2番目の値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true``a`がに等しい場合にのみ `b` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```