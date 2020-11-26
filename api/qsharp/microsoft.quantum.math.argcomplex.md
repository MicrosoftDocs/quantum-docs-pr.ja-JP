---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 259296f397207cde4a7d6dfe6cfb1a18e8055216
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211102"
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