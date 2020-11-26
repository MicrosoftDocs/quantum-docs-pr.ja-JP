---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: P# listringfromgenidx 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: a937dc648c5de5a5f6de7da996448af497b92185
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230312"
---
# <a name="paulistringfromgenidx-function"></a>P# listringfromgenidx 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


によって記述される psystem.string li 文字列とその qubit インデックスを抽出し `GeneratorIndex` ます。

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a>入力

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` Pをエンコードする型。



## <a name="output--pauliint"></a>出力: ([P# li](xref:microsoft.quantum.lang-ref.pauli)[]、[Int](xref:microsoft.quantum.lang-ref.int)[])

によって記述された用語の P# li 文字列と、その処理を `GeneratorIndex` 行う qubits へのインデックス。