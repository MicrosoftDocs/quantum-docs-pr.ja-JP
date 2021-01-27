---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: Inttop/Li 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 76f482b86ff4a27b6e6ce6ae4ec3d59422563f12
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842247"
---
# <a name="inttopauli-function"></a>Inttop/Li 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


整数をシングル qubit の P# li 演算子に変換します。

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>入力

### <a name="idx--int"></a>idx: [Int](xref:microsoft.quantum.lang-ref.int)

`0..3`P# li 演算子に変換する範囲の整数。



## <a name="output--pauli"></a>出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`によって指定された演算子 `[PauliI, PauliX, PauliY, PauliZ][idx]` 。