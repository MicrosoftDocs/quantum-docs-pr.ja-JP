---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 6904054bb1aff3a57c80882694b4c217812b2b81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842239"
---
# <a name="intstopaulis-function"></a>IntsToPaulis 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


整数の配列をシングル qubit の演算子の配列に変換します。

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>入力

### <a name="ints--int"></a>Int: [Int](xref:microsoft.quantum.lang-ref.int)[]

`0..3`P# li 演算子に変換される範囲内の整数の配列。



## <a name="output--pauli"></a>出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]

`paulis` `Pauli[]` `ints` `paulis[idxPauli]` `[PauliI, PauliX, PauliY, PauliZ]` によって指定されたの要素と同じ長さの、p# li 演算子の配列 `ints[idxPauli]` 。