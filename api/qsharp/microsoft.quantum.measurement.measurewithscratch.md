---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 4173aa9daac08a3febdfcbf12dc236f797685436
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854657"
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