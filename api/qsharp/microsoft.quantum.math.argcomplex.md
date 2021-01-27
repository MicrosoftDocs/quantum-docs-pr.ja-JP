---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: e8ce73a43940ab0ed66338f962cc6f76fc2b694b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842752"
---
# <a name="argcomplex-function"></a>ArgComplex 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


型の複素数のフェーズを返し `Complex` ます。

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>入力

### <a name="input--complex"></a>入力: [Complex](xref:Microsoft.Quantum.Math.Complex)

複素数 $c = x + i y $。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

フェーズ $ \ text{arg} [c] = \text{ArcTan} (y, x) \ in (--pi, \ pi] $。