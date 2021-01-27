---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: Apply乗数 Ycontrol/operation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: ac3972287d55ed2df85e1d88510918cc5202c711
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844855"
---
# <a name="applymultiplycontrolledand-operation"></a>Apply乗数 Ycontrol/operation

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ターゲット qubit が初期化されていることを前提として、複数の制御を行う Toffoli ゲートを実装します。  Adjoint 操作では、ターゲットの qubit が0にリセットされることを前提としています。

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a>入力

### <a name="controls--qubit"></a>コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

制御 qubits


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

ターゲット qubit



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

