---
uid: Microsoft.Quantum.Logical.EqualR
title: EqualR 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 9ce29f2868f092001a3dca23a2913a3963ac70fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815974"
---
# <a name="equalr-function"></a>EqualR 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2つの入力が等しい場合にのみ true を返します。

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>入力

### <a name="a--__invalidresult__"></a>a:__無効 <Result>__

比較する最初の値。


### <a name="b--__invalidresult__"></a>b:__無効 <Result>__

比較する2番目の値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true``a`がに等しい場合にのみ `b` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```qsharp
let cond = a == b;
let cond = EqualR(a, b);
```