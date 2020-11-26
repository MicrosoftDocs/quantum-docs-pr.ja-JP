---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Applyの Mimionicswap 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218803"
---
# <a name="applyfermionicswap-operation"></a>Applyの Mimionicswap 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fermionic SWAP を適用します。

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

これは基本的に、-1 のグローバルフェーズを適用しているときに、両方の qubits が1である場合に、qubits を交換します。 Orbitals の symmetrization を保持します。
詳細については、「」をご覧ください。

この操作は、\begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 0 & 0 & 1 & 0 0 & 1 & 0 & 0 \\ \\ \\ \\ \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}. によって表されます。
\end{align}

## <a name="input"></a>入力

### <a name="qubit1--qubit"></a>qubit1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

交換される最初の qubit。


### <a name="qubit2--qubit"></a>qubit2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

スワップする2番目の qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>リファレンス

- [*ライアン Babbush、Nathan Wiebe、Jarrod McClean、James Mcclアイン、Hartmut Neven、Garnet Kin-Lic チャン*、arxiv: 1706.00023](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a>参照

- [Microsoft.... SWAP](xref:Microsoft.Quantum.Intrinsic.SWAP)