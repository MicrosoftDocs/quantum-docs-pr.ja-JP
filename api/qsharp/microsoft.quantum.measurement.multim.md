---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: b7f4083bde84c204611ea33746ae351a3e27b946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857009"
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