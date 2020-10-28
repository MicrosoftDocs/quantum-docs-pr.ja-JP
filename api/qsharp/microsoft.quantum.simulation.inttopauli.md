---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: Inttop/Li 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724847"
---
# <a name="inttopauli-function"></a>Inttop/Li 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


整数をシングル qubit の P# li 演算子に変換します。

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>入力

### <a name="idx--int"></a>idx: [Int](xref:microsoft.quantum.lang-ref.int)

`0..3`P# li 演算子に変換する範囲の整数。



## <a name="output--pauli"></a>出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`によって指定された演算子 `[PauliI, PauliX, PauliY, PauliZ][idx]` 。