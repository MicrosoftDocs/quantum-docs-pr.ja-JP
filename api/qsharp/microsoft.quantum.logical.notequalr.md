---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709793"
---
# <a name="notequalr-function"></a>NotEqualR 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パック [](https://nuget.org/packages/)


2つの入力が等しくない場合にのみ true を返します。

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>入力

### <a name="a--__invalidresult__"></a>a: __無効 <Result>__

比較する最初の値。


### <a name="b--__invalidresult__"></a>b: __無効 <Result>__

比較する2番目の値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true``a`がと等しくない場合にのみ `b` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```