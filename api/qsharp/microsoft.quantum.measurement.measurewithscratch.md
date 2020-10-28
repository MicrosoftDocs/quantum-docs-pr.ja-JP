---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720326"
---
# <a name="measurewithscratch-operation"></a>MeasureWithScratch 操作

名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)

パック [](https://nuget.org/packages/)


明示的なスクラッチ qubit を使用して測定を実行し、指定された Pan Li 演算子を測定します。

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a>入力

### <a name="pauli--pauli"></a>[p# li []](xref:microsoft.quantum.lang-ref.pauli)

シングル qubit の P# li 演算子の配列として指定されたマルチ qubit の Pan Li 演算子。


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

測定する qubit レジスタ。



## <a name="output--__invalidresult__"></a>出力: __無効 <Result>__

レジスタに対して指定された P# li 演算子を測定した結果 `target` 。