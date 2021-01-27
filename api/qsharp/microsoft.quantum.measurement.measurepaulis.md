---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853780"
---
# <a name="measurepaulis-operation"></a>MeasurePaulis 操作

名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


複数のマルチビット演算子の配列を指定すると、指定された測定ガジェットを使用してそれぞれを測定し、結果の配列を返します。

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>入力

### <a name="paulis--pauli"></a>paulis: [p li](xref:microsoft.quantum.lang-ref.pauli)[] []

測定するマルチ qubit の演算子の配列。


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

指定された演算子を測定するための登録です。


### <a name="gadget--pauliqubit--__invalidresult__"></a>ガジェット: ([p、li](xref:microsoft.quantum.lang-ref.pauli)[]、[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) =__無効 <Result>__> 

指定されたマルチ qubit 演算子の測定値を実行する演算。



## <a name="output--__invalidresult__"></a>出力:__無効 <Result> な__[]

の各要素を測定して取得した結果の配列 `paulis` `target` 。