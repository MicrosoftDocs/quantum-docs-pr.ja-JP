---
uid: Microsoft.Quantum.Math.ComplexPolarAsComplex
title: ComplexPolarAsComplex 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolarAsComplex
qsharp.summary: Converts a complex number of type `ComplexPolar` to a complex number of type `Complex`.
ms.openlocfilehash: ace458ec168b70a873fae2a4990b9a427efac7cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228612"
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