---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713153"
---
# <a name="_assertequalonbasisvector-operation"></a>_assertEqualOnBasisVector 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


2つの操作を適用した結果が同じであるかどうかを確認し `givenU` `expectedU` ます。 ベース状態は、パラメーターによって記述され `basis` ます。
<xref:microsoft.quantum.extensions.fliptobasis>この説明の詳細については、「関数」を参照してください。

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>入力

### <a name="basis--int"></a>ベース: [Int](xref:microsoft.quantum.lang-ref.int)[]

$N $ qubit のそれぞれに対して、単一 qubit basis 状態 ID (0 <= ID <= 3) で指定された基礎状態。


### <a name="givenu--qubit--unit"></a>与え u: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

$N $ qubits の操作を確認します。


### <a name="expectedu--qubit--unit-adj"></a>expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

$N $ qubits に対する参照操作が、と比較されます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

