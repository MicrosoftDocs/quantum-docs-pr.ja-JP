---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: ApplyCNOTChain 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: e237e4424661de816e73b0c78523180b41190cf9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219143"
---
# <a name="applycnotchain-operation"></a>ApplyCNOTChain 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Qubits のレジスタのパリティを計算します。

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

この操作では、入力の状態を $ $ \begin{align} \ket{q_0} \ket{q_1} \ cドット \ket{q_ {n-1}} & \ map\ket{q_0} \ket{q_0 \ oplus q_1} \ket{q_0/oplus q_1 \ oplus q_2} \ cドット \ket{q_0 \ oplus/cドット/oplus q_ {n-1}} として変換します。
\end{align} $ $

## <a name="input"></a>入力

### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

パリティを計算および格納する qubits の配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

