---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Istate 操作の実行中
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: 8b2917a7d9414539f2f7c821c4115fc4b21d0373
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724002"
---
# <a name="preparechoistate-operation"></a>Istate 操作の実行中

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パック [](https://nuget.org/packages/)


指定された操作について、指定された参照およびターゲットレジスタに Jamiłkowski 状態を準備します。

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="op--qubit--unit"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

操作 $ \ ラムダ $ Jamiłkowski state $J (-ラムダ)/2 ^ N $ を準備します。ここで $N $ は、が動作する qubits の数です `op` 。


### <a name="reference--qubit"></a>参照: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

のアクションの参照として使用される、$ \ket{00\cdots 0} $ 状態から始まる qubits のレジスタ `op` 。


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

が適用される $ \ket{00\cdots 0} $ 状態の最初の qubits のレジスタ `op` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

Jamiłkowski state $J (-ラムダ) $ of クォンタムプロセスは、$ $ \begin{align} J (\ ラムダ) \mathrel{: =} として定義されています (& a)。 (& a) J (& a): =} (& \! \! )、\langle\boldone $ $ where $ |X\rangle \! \rangle $ は、列スタック規則内のマトリックス $X $ の *ベクター化* です。 この状態についての従来の説明を学習すると、任意の入力状態に作用する $-ラムダ $ の効果に関する完全な情報が得られ、 *量子プロセス tomography* の基盤が形成されます。

## <a name="see-also"></a>参照

- [Microsoft......... この Istatea](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [Microsoft...... 準備](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [PrepareChoiStateCA の準備](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)