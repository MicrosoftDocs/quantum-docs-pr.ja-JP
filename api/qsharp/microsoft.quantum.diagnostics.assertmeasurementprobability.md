---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 2fd89121516ef6994dedb75b214589b4e360ff8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830819"
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



## <a name="example"></a>例

```qsharp
using (register = Qubit()) {
    H(register);
    AssertProb([PauliZ], [register], One, 0.5,
        "Measuring in conjugate basis did not give 50/50 results.", 1e-5);
}
```

## <a name="remarks"></a>解説

この操作の Adjoint および制御されたバージョンが条件をチェックしないことに注意してください。

## <a name="see-also"></a>参照

- [AssertMeasurement です。](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)