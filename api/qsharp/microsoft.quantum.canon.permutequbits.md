---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 0f4d8819d5b08f4d5370f8fdc407b2eb2a3e5f21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715659"
---
# <a name="permutequbits-operation"></a>PermuteQubits 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


スワップ操作を使用した Permutes qubits。

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="ordering--int"></a>順序付け: [Int](xref:microsoft.quantum.lang-ref.int)[]

Qubits の新しい順序について説明します。ここで、インデックス i の qubits は [i] の順に並べられます。


### <a name="register--qubit"></a>register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

操作する qubit レジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

