---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f88ae08f45c284f65151419c214705c74c3fadac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814505"
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

```qsharp
let cond = a != b;
let cond = NotEqualI(a, b);
```