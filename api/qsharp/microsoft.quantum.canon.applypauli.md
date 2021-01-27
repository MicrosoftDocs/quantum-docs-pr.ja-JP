---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: 実行操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: b3557c6d8b5a90019f6d4cfa7b405475a3ab39fb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844754"
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



## <a name="example"></a>例

同等のものを次に示します。

```qsharp
ApplyPauli([PauliY, PauliZ, PauliX], target);
```

and

```qsharp
Y(target[0]);
Z(target[1]);
X(target[2]);
```