---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: 36de9dbdfc96f6e1698ee4537405f7cb74e44262
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711039"
---
# <a name="multim-operation"></a>MultiM 操作

名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)

パック [](https://nuget.org/packages/)


指定された配列内の各 qubit を標準ベースで測定します。

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a>入力

### <a name="targets--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

測定する qubits の配列。



## <a name="output--__invalidresult__"></a>出力: __無効 <Result> な__ []

測定結果の配列。