---
uid: Microsoft.Quantum.Math.ComplexAsComplexPolar
title: ComplexAsComplexPolar 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexAsComplexPolar
qsharp.summary: Converts a complex number of type `Complex` to a complex number of type `ComplexPolar`.
ms.openlocfilehash: b66ed56e2c7229d7b86a71a43e6672cfde97fb59
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709653"
---
# <a name="complexascomplexpolar-function"></a>ComplexAsComplexPolar 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パック [](https://nuget.org/packages/)


複素数型の複素数を `Complex` 型の複素数に変換 `ComplexPolar` します。

```qsharp
function ComplexAsComplexPolar (input : Microsoft.Quantum.Math.Complex) : Microsoft.Quantum.Math.ComplexPolar
```


## <a name="input"></a>入力

### <a name="input--complex"></a>入力: [Complex](xref:Microsoft.Quantum.Math.Complex)

複素数 $c = x + i y $。



## <a name="output--complexpolar"></a>出力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)

複素数 $c = r e ^ {i t} $。