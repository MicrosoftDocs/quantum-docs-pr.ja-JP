---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: ba1a4e99c411a4718b5a09fdcd57a7239eb4dbd6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845114"
---
# <a name="applycnotchainwithtarget-operation"></a>ApplyCNOTChainWithTarget 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Qubits の配列のパリティをターゲットの qubits に計算します。

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

配列の初期状態が $ \ket{q_0} \ket{q_1} \ket{の場合は q_ {\ text{target{1}} $, 最終的な状態は、$ \ket{q_0} \ket{q_1 \ oplus q_0} \ cドット \ket{q_ {n-1} \ oplus/cドット \ oplus q_0 {/text{target{1}} $ によって指定されます。

## <a name="input"></a>入力

### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

パリティが計算される qubits の配列。


### <a name="targetqubit--qubit"></a>targetQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

' Qubit ' のパリティが Xor される最後の qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

同等のものを次に示します。

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

and

```qsharp
ApplyCNOTChain(qs);
```