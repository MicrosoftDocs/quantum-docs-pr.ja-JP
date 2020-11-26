---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dc132cbab556bd4b5d5c557ad267f1839e8039fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197213"
---
# <a name="notequali-function"></a>NotEqualI 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2つの入力が等しくない場合にのみ true を返します。

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>入力

### <a name="a--int"></a>a: [Int](xref:microsoft.quantum.lang-ref.int)

比較する最初の値。


### <a name="b--int"></a>b: [Int](xref:microsoft.quantum.lang-ref.int)

比較する2番目の値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true``a`がと等しくない場合にのみ `b` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```