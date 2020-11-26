---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: 6c048c17df21d1026dc671f30d72a13ed8d8b7f5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200630"
---
# <a name="measurestabilizergenerators-operation"></a>MeasureStabilizerGenerators 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


安定板グループの特定のジェネレーターセットを測定します。

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a>入力

### <a name="stabilizergroup--pauli"></a>stabilizerGroup: [p li](xref:microsoft.quantum.lang-ref.pauli)[] []

Multiqubit P# li 演算子の配列。
たとえば、 `stabilizerGroup[0]` は、シングル qubit の P# li マトリックスのリストです。これは、安定板のジェネレーターです。


### <a name="logicalregister--logicalregister"></a>logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

安定板のコードが定義されている qubits の配列。


### <a name="gadget--pauliqubit--__invalidresult__"></a>ガジェット: ([p、li](xref:microsoft.quantum.lang-ref.pauli)[]、[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) =__無効 <Result>__> 

Multiqubit の P# li 演算子を測定する方法を指定する操作。



## <a name="output--syndrome"></a>出力: [より隣人](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

測定の結果。

## <a name="remarks"></a>解説

これは、指定されたジェネレーターのセットが通勤されているかどうかを確認しません。
通勤でない場合は、測定の結果が任意である可能性があります。