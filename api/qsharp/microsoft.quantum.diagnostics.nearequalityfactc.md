---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactC
title: NearEqualityFactC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactC
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: aef4925452fe2de444b1995f92b8fe1a2894834a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712663"
---
# <a name="nearequalityfactc-function"></a>NearEqualityFactC 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


古典的な複素数の値が、最小許容範囲である 1e-10 になるようにアサートします。

```qsharp
function NearEqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex) : Unit
```


## <a name="input"></a>入力

### <a name="actual--complex"></a>実績: [Complex](xref:Microsoft.Quantum.Math.Complex)

確認する数値。


### <a name="expected--complex"></a>必要: [Complex](xref:Microsoft.Quantum.Math.Complex)

予期される値。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

