---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: 実行操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: 7f42d9cab2f80f8f826ad1268b050134f0540cdd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218225"
---
# <a name="applypauli-operation"></a>実行操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された複数の演算子がある場合、対応する操作をレジスタに適用します。

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="pauli--pauli"></a>[p# li []](xref:microsoft.quantum.lang-ref.pauli)

シングル qubit の P# li 演算子の配列として表されるマルチ qubit の Pan Li 演算子。


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

を登録して、に指定された P# li 操作を適用します。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

