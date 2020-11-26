---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: ApplyAndChain 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: c53bca6ecf964f4358b0a7ff1c61d4e8e195cd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219364"
---
# <a name="applyandchain-operation"></a>ApplyAndChain 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ゲートとゲートのチェーンを計算します

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a>説明

一時的な結果を計算する補助 qubits を明示的に指定する必要があります。
少なくとも2つのコントロールがある場合、そのレジスタの長さはになり `Length(ctrlRegister) - 2` ます。それ以外の場合は、長さが0になります。

## <a name="input"></a>入力

### <a name="auxregister--qubit"></a>auxRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="ctrlregister--qubit"></a>ctrlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

