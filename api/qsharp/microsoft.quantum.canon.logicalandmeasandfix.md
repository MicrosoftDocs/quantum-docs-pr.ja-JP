---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715925"
---
# <a name="logicalandmeasandfix-operation"></a>LogicalANDMeasAndFix 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


複数の qubits の論理 AND を計算します。

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="ctrlregister--qubit"></a>ctrlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

複数の入力およびゲートへの qubits 入力。


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

およびの出力が書き込まれる qubit。 これは、常に $ \ket $ 状態で開始することを前提としてい {0} ます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

`ctrlRegister`が完全に $2 $ qubits である場合、これは操作と同じですが、フェーズ `CCNOT` $e ^ {i \ pi/2} $ on $ \ket {001} $ および $-e ^ {i \ pi/2} $ on $ \ket {101} $ と $ \ket $ に相当し {011} ます。
Adjoint は、メジャーおよび修正アプローチでもあります。これは、元の操作を特殊なケース (参照を参照) でのみ逆にしたものですが、使用する T ゲートの数が減ります。

## <a name="references"></a>関連項目

- [*Gidney* 、1709.06648](https://arxiv.org/abs/1709.06648)