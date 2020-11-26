---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 97a55b4bb85095c7d8e8432dfcd1c6d6f7e93cdc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223937"
---
# <a name="_prepareentangledstate-operation"></a>_prepareEntangledState 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


2つのレジスタが指定されている場合、によって、各レジスタの qubits の各ペアの間に下回っあり状態が準備されます。
すべての qubits は、| 0 ⟩状態で開始する必要があります。

結果として、各レジスタからの対応する qubits のペアは、$ \ket{\ {beta_ {00} } beta_ {00} } $ にあります。

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="left--qubit"></a>left: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cdots 0} $ 状態の qubit 配列


### <a name="right--qubit"></a>right: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cdots 0} $ 状態の qubit 配列



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

