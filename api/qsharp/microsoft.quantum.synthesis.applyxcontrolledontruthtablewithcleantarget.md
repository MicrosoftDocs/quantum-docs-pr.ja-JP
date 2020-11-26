---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: ApplyXControlledOnTruthTableWithCleanTarget 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 904ff7e2e7e81ee966846af120e9427f4e92301c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203265"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a>ApplyXControlledOnTruthTableWithCleanTarget 操作

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


の @"microsoft.quantum.intrinsic.x" `target` クラシック代入に対してブール関数が true と評価された場合に、操作をに適用し `func` `controlRegister` ます。

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

この操作では、の特殊なケースを実装します。この場合、 @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" ターゲットの qubit は $ \ket $ 状態であることがわかってい {0} ます。

実装では @"microsoft.quantum.intrinsic.cnot" 、およびゲートを使用し @"microsoft.quantum.intrinsic.r1" ます。  Adjoint 操作の実装は最適化されており、測定ベースの uncomputation が使用されます。

## <a name="input"></a>入力

### <a name="func--bigint"></a>func: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

ブール型の真理値テーブルを大きな整数として表現


### <a name="controlregister--qubit"></a>controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

制御 qubits の登録


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

ターゲット qubit ($ \ket $ 状態である必要があります {0} )



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [ApplyXControlledOnTruthTable です。](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)