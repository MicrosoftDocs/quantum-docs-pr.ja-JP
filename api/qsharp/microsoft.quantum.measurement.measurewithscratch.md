---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: c42316a811e0e4a81c7f244c093a2be88fe5c733
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227065"
---
# <a name="measurewithscratch-operation"></a>MeasureWithScratch 操作

名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


明示的なスクラッチ qubit を使用して測定を実行し、指定された Pan Li 演算子を測定します。

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a>入力

### <a name="pauli--pauli"></a>[p# li []](xref:microsoft.quantum.lang-ref.pauli)

シングル qubit の P# li 演算子の配列として指定されたマルチ qubit の Pan Li 演算子。


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

測定する qubit レジスタ。



## <a name="output--__invalidresult__"></a>出力:__無効 <Result>__

レジスタに対して指定された P# li 演算子を測定した結果 `target` 。