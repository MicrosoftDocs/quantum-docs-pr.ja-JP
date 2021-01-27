---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: PreparePauliEigenstate 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: 473bb2fa4429a14f69bcae4573354aad87dc37df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854358"
---
# <a name="preparepaulieigenstate-operation"></a>PreparePauliEigenstate 操作

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された Pauli 演算子の正の eigenstate で qubit を準備します。
Id 演算子が指定されている場合、qubit は下回っ mixed 状態で準備されます。

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a>説明

Qubit が最初に $ \ket $ 状態であった場合 {0} 、この操作は、指定された p li 演算子の $ + $1 eigenstate の qubit を準備します。または、の場合は、 `PauliI` 代わりに下回っ mixed 状態 (を参照) で qubit を準備し <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ます。

Qubit が $ \ket $ 以外の状態であった場合 {0} 、この操作では次のゲートが適用されます。 $H $ for `PauliX` 、$HS $ for `PauliY` 、$I $ for `PauliZ` および <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI` 。

## <a name="input"></a>入力

### <a name="basis--pauli"></a>基礎: [P# li](xref:microsoft.quantum.lang-ref.pauli)

P$P Li 演算子は $ です。


### <a name="qubit--qubit"></a>qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

準備する qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>例

$ \Ket{+} $ 状態で qubit を準備するには、次のようにします。

```qsharp
using (q = Qubit()) {
    PreparePauliEigenstate(PauliX, qubit);
    // ...
}
```