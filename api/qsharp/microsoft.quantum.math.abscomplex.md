---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d9afb4b9b37b6cdd83bfd3829d3174d769c5f41b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211391"
---
# <a name="abscomplex-function"></a>AbsComplex 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


型の複素数の絶対値を返し `Complex` ます。

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>入力

### <a name="input--complex"></a>入力: [Complex](xref:Microsoft.Quantum.Math.Complex)

複素数 $c = x + i y $。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

絶対値 $ | c |= \ sqrt{x ^ 2 + y ^ 2} $。