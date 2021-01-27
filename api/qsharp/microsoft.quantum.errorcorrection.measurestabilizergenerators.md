---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: d7c8df079e49b2ce0a5106e430ef4060df85cdc4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825764"
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