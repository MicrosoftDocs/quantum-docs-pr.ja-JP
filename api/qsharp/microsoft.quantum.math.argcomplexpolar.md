---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 7088397bd60e2779ef60afc1bb7108d937a62c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195768"
---
# <a name="argcomplexpolar-function"></a>ArgComplexPolar 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


型の複素数のフェーズを返し `ComplexPolar` ます。

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a>入力

### <a name="input--complexpolar"></a>入力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)

複素数 $c = r e ^ {i t} $。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

フェーズ $ \ text{arg} [c] = t $。