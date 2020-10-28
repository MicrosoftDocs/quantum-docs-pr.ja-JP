---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709452"
---
# <a name="intstopaulis-function"></a>IntsToPaulis 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


整数の配列をシングル qubit の演算子の配列に変換します。

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>入力

### <a name="ints--int"></a>Int: [Int](xref:microsoft.quantum.lang-ref.int)[]

`0..3`P# li 演算子に変換される範囲内の整数の配列。



## <a name="output--pauli"></a>出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]

`paulis` `Pauli[]` `ints` `paulis[idxPauli]` `[PauliI, PauliX, PauliY, PauliZ]` によって指定されたの要素と同じ長さの、p# li 演算子の配列 `ints[idxPauli]` 。