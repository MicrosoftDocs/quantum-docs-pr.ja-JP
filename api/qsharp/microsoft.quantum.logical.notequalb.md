---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: d5a9819bf3baa7c914487277fef308abbc8d25bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709835"
---
# <a name="notequalb-function"></a>NotEqualB 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パック [](https://nuget.org/packages/)


2つの入力が等しくない場合にのみ true を返します。

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>入力

### <a name="a--bool"></a>a: [Bool](xref:microsoft.quantum.lang-ref.bool)

比較する最初の値。


### <a name="b--bool"></a>b: [Bool](xref:microsoft.quantum.lang-ref.bool)

比較する2番目の値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true``a`がと等しくない場合にのみ `b` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```