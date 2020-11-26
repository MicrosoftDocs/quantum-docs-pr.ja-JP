---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 032b9224ad728f0637596668c2928a889deeba55
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202364"
---
# <a name="assertmeasurementprobability-operation"></a>AssertMeasurementProbability 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


指定された型の指定された qubits を測定すると、特定の確率で特定の結果が許容範囲内にあることをアサートします。

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="bases--pauli"></a>ベース: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]

の確率をアサートする測定効果。これは、マルチ qubit の P# li 演算子として表現されます。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

アサーションを行うレジスタ。


### <a name="result--__invalidresult__"></a>結果:__無効 <Result>__

の予期される結果 `Measure(bases, qubits)` 。


### <a name="prob--double"></a>: [ダブル](xref:microsoft.quantum.lang-ref.double)

指定された結果が返される確率。


### <a name="msg--string"></a>msg: [文字列](xref:microsoft.quantum.lang-ref.string)

アサーションが失敗した場合に報告されるメッセージ。


### <a name="tol--double"></a>を: [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

この操作の Adjoint および制御されたバージョンが条件をチェックしないことに注意してください。

## <a name="see-also"></a>参照

- [AssertMeasurement です。](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)