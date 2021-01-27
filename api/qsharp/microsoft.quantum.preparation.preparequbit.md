---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: PrepareQubit 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  > [!WARNING]

  > PrepareQubit has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.


  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: e6a88ccf4c01b2f0a7344e3823b2748790cf9650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854333"
---
# <a name="preparequbit-operation"></a>PrepareQubit 操作

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> PrepareQubit は非推奨となりました。 代わりに、<xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> を使用してください。

`Zero`指定された Pauli 演算子の + 1 () eigenstate で qubit を準備します。
Id 演算子が指定されている場合、qubit は下回っ mixed 状態で準備されます。

Qubit が最初に $ \ket $ 状態であった場合 {0} 、この操作は、指定された p li 演算子の $ + $1 eigenstate の qubit を準備します。または、の場合は、 `PauliI` 代わりに下回っ mixed 状態 (を参照) で qubit を準備し <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ます。

Qubit が $ \ket $ 以外の状態であった場合 {0} 、この操作では次のゲートが適用されます。 $H $ for `PauliX` 、$HS $ for `PauliY` 、$I $ for `PauliZ` および <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI` 。

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="basis--pauli"></a>基礎: [P# li](xref:microsoft.quantum.lang-ref.pauli)

P$P Li 演算子は $ です。


### <a name="qubit--qubit"></a>qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

準備する qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

