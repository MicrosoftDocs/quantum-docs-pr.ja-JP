---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: ApplyOpRepeatedlyOverC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 08c3af3a4877481833973061aa4d54c2b29304c9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218259"
---
# <a name="applyoprepeatedlyoverc-operation"></a>ApplyOpRepeatedlyOverC 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Qubit レジスタに対して同じ操作を複数回適用します。

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>入力

### <a name="op--qubit--unit--is-ctl"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl

Qubit レジスタに複数回適用される操作


### <a name="targets--int"></a>ターゲット: [Int](xref:microsoft.quantum.lang-ref.int)[] []

Op のターゲットを記述する入れ子になった配列。 各配列には、使用する qubits を記述する整数のリストを含める必要があります。


### <a name="register--qubit"></a>register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

操作する qubit レジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [Microsoft....。](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)