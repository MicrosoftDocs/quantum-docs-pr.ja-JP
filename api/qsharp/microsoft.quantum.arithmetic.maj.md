---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: c1801d1d7ed04ead11b672f24d44a94989cf8f1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721015"
---
# <a name="maj-operation"></a>MAJ 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


これにより、インプレースマジョリティ操作が3つの qubits に適用されます。

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a>説明

ターゲットの qubit を $ \ket{z} $ として、入力 qubit の入力状態を $ \ket{x} $ および $ \ket{y} $ として示す場合、この操作では次の変換が実行されます: $ \ket{xyz} \rightarrow \ket{x、oplus z} \ket{y/oplus z} \ket{\operatorname{MAJ} (x, y, z)} $。

## <a name="input"></a>入力

### <a name="input0--qubit"></a>input0: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

最初の入力 qubit。


### <a name="input1--qubit"></a>input1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

2番目の入力 qubit。


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

マジョリティ関数が適用される qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

