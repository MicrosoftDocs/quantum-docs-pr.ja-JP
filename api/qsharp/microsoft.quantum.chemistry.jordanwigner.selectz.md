---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: SelectZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 171bbe28ce8f10ca4b213a94b23f8c049546e3bf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713792"
---
# <a name="selectz-operation"></a>SelectZ 操作

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


インデックス状態 $ \ket{p} $ に対して、qubits $p $ 条件付きで p Li $Z $ gate を適用する、$U のインデックス番号。 つまり、$ $ \begin{align} U\ket {p} \ k {\ psi} = \ket{p}Z \_ p\ket {\ psi} \end{align} $ $

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

このレジスタの状態 $ \ket{p} $ によって、$Z $ が適用される qubit が決まります。


### <a name="targetregister--qubit"></a>targetRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Pare Li 演算子が適用される qubits の登録です。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

