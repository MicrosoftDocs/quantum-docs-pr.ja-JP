---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: e3175b9b6fd2890963de0452102e2f0de1026b91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198233"
---
# <a name="equalcp-function"></a>EqualCP 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2つの入力が等しい場合にのみ true を返します。

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a>入力

### <a name="a--complexpolar"></a>a: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)

比較する最初の値。


### <a name="b--complexpolar"></a>b: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)

比較する2番目の値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true``a`がに等しい場合にのみ `b` 。