---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226997"
---
# <a name="multim-operation"></a>MultiM 操作

名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された配列内の各 qubit を標準ベースで測定します。

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a>入力

### <a name="targets--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

測定する qubits の配列。



## <a name="output--__invalidresult__"></a>出力:__無効 <Result> な__[]

測定結果の配列。