---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: ApplyUnitary 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859217"
---
# <a name="applyunitary-operation"></a>ApplyUnitary 操作

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2 ^ n x 2 ^ n のユニタリ行列で定義されているゲートを適用します。

マトリックスがユニタリでない場合、またはサイズが間違っている場合に失敗します。

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="unitary--complex"></a>ユニタリ: [Complex](xref:Microsoft.Quantum.Math.Complex)[] []

操作を説明する 2 ^ n x 2 ^ n のユニタリ行列。
マトリックスがユニタリでない場合、または適切なサイズでない場合、は例外をスローします。


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

に、長さ n の操作レジスタを適用する qubits を指定します。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

