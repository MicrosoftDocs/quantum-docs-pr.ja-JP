---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 3fbe000202abbd8a206b0c83dfa35f4546ea91cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202449"
---
# <a name="assertmeasurement-operation"></a>AssertMeasurement 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


指定された P# li の指定した qubits を測定すると、常に指定された結果が得られることをアサートします。

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="bases--pauli"></a>ベース: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]

の確率をアサートする測定効果。これは、マルチ qubit の P# li 演算子として表現されます。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

アサーションを行うレジスタ。


### <a name="result--__invalidresult__"></a>結果:__無効 <Result>__

の予期される結果 `Measure(bases, qubits)` 。


### <a name="msg--string"></a>msg: [文字列](xref:microsoft.quantum.lang-ref.string)

アサーションが失敗した場合に報告されるメッセージ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

この操作の Adjoint および制御されたバージョンが条件をチェックしないことに注意してください。

## <a name="see-also"></a>参照

- [AssertMeasurementProbability です。](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)