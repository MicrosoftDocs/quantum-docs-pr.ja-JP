---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 1d62d25a3d04c431440cf8fc1eb585cac2c73f2e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712658"
---
# <a name="nearequalityfactcp-function"></a>NearEqualityFactCP 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


古典的な複素数の値が、最小許容範囲である 1e-10 になるようにアサートします。

```qsharp
function NearEqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar) : Unit
```


## <a name="input"></a>入力

### <a name="actual--complexpolar"></a>実績: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)

確認する数値。


### <a name="expected--complexpolar"></a>期待される結果: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)

予期される値。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

