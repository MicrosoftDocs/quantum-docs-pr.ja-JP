---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: ApplyPauliFromBitString 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: e0edd8420127339116e525421ba23e246dcf0a45
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841583"
---
# <a name="applypaulifrombitstring-operation"></a>ApplyPauliFromBitString 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ブール値配列の対応するビットが指定された入力と一致する場合、配列内の各 qubit に対して P# li 演算子を適用します。

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="pauli--pauli"></a>p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li

Where に適用する p# li 演算子 `qubits[idx]``bitsApply == bits[idx]`


### <a name="bitapply--bool"></a>bitApply: [Bool](xref:microsoft.quantum.lang-ref.bool)

bit がこの値の場合は P# li を適用します


### <a name="bits--bool"></a>bits: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

の対応する qubit を指定するブールレジスタ `qubits`


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

指定された P# li 演算子を選択的に適用するクォンタムレジスタ



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

ブール型の配列とクォンタムレジスタは同じ長さである必要があります。