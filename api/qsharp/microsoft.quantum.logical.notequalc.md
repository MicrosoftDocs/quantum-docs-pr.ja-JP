---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 0be2c97ec7b0350fc20eace76746f3ffff65fd52
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197366"
---
# <a name="notequalc-function"></a>NotEqualC 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2つの入力が等しくない場合にのみ true を返します。

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a>入力

### <a name="a--complex"></a>a: [Complex](xref:Microsoft.Quantum.Math.Complex)

比較する最初の値。


### <a name="b--complex"></a>b: [Complex](xref:Microsoft.Quantum.Math.Complex)

比較する2番目の値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true``a`がと等しくない場合にのみ `b` 。