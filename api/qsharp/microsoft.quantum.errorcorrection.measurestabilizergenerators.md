---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712266"
---
# <a name="measurestabilizergenerators-operation"></a>MeasureStabilizerGenerators 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


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


### <a name="gadget--pauliqubit--__invalidresult__"></a>ガジェット: ( [p、li](xref:microsoft.quantum.lang-ref.pauli)[]、 [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = __無効 <Result>__ > 

Multiqubit の P# li 演算子を測定する方法を指定する操作。



## <a name="output--syndrome"></a>出力: [より隣人](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

測定の結果。

## <a name="remarks"></a>解説

これは、指定されたジェネレーターのセットが通勤されているかどうかを確認しません。
通勤でない場合は、測定の結果が任意である可能性があります。