---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d47e04616d4bcf49273bec31fc22990a8244962b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723890"
---
# <a name="abscomplex-function"></a>AbsComplex 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パック [](https://nuget.org/packages/)


型の複素数の絶対値を返し `Complex` ます。

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>入力

### <a name="input--complex"></a>入力: [Complex](xref:Microsoft.Quantum.Math.Complex)

複素数 $c = x + i y $。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

絶対値 $ | c |= \ sqrt{x ^ 2 + y ^ 2} $。