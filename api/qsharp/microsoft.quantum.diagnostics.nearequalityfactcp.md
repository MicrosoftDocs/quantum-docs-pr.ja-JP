---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 477449913732950ad26adc0cdabaaaab803a20c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853280"
---
# <a name="nearequalityfactcp-function"></a>NearEqualityFactCP 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

