---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830075"
---
# <a name="assertphase-operation"></a>AssertPhase 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>例

次のアサートが成功しました: `qubit` is in state $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ k {0} + e ^ {i 0.5} \ sqrt {1/2} \ k {1} $;

- `AssertPhase(0.0,qubit,10e-10);`

`qubit` 状態は、$ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ k {0} + e ^ {-i 0.5} \ sqrt {1/2} \ k {1} $; です

- `AssertPhase(0.5,qubit,10e-10);`

`qubit` 状態は、$ \ket{\psi} = e ^ {-i 2.2} \ sqrt {1/2} \ k {0} + e ^ {i 0.2} \ sqrt {1/2} \ k {1} $; です

- `AssertPhase(-1.2,qubit,10e-10);`