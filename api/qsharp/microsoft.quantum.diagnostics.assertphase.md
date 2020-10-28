---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: e042c03d2a72d9ce4816a8cdb56603e175b22807
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712952"
---
# <a name="assertphase-operation"></a>AssertPhase 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


等しい法則状態のフェーズに予期される値があることをアサートします。

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>説明

この操作では、 {2} {0} 任意の real $t $ に対して $ \frac{e ^ {i t}} {\ sqrt} (e ^ {k} \ k) $ として表現されるクォンタムの状態のフェーズ $/phi $ が、予期される値であることをアサートし {1} ます。

## <a name="input"></a>入力

### <a name="expected--double"></a>が必要です。 [Double](xref:microsoft.quantum.lang-ref.double)

期待される値 $ \ phi \ in (-\ pi, \ pi) $。


### <a name="qubit--qubit"></a>qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

予期される状態を格納する qubit。


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

実際と予想される差に対する絶対許容値。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

