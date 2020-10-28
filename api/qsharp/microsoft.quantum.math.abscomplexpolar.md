---
uid: Microsoft.Quantum.Math.AbsComplexPolar
title: AbsComplexPolar 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplexPolar
qsharp.summary: Returns the absolute value of a complex number of type `ComplexPolar`.
ms.openlocfilehash: bc74d691e69a4f1be096582e42ec3a88ddcdd3c0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723881"
---
# <a name="abscomplexpolar-function"></a>AbsComplexPolar 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パック [](https://nuget.org/packages/)


型の複素数の絶対値を返し `ComplexPolar` ます。

```qsharp
function AbsComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a>入力

### <a name="input--complexpolar"></a>入力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)

複素数 $c = r e ^ {i t} $。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

絶対値 $ | c |= r $。