---
uid: Microsoft.Quantum.Math.ComplexPolarAsComplex
title: ComplexPolarAsComplex 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolarAsComplex
qsharp.summary: Converts a complex number of type `ComplexPolar` to a complex number of type `Complex`.
ms.openlocfilehash: 6834b47705d080d4597ae1a6037462521fac45f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853869"
---
# <a name="complexpolarascomplex-function"></a>ComplexPolarAsComplex 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


複素数型の複素数を `ComplexPolar` 型の複素数に変換 `Complex` します。

```qsharp
function ComplexPolarAsComplex (input : Microsoft.Quantum.Math.ComplexPolar) : Microsoft.Quantum.Math.Complex
```


## <a name="input"></a>入力

### <a name="input--complexpolar"></a>入力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)

複素数 $c = r e ^ {i t} $。



## <a name="output--complex"></a>出力: [Complex](xref:Microsoft.Quantum.Math.Complex)

複素数 $c = x + i y $。