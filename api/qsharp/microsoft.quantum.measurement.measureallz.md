---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227082"
---
# <a name="measureallz-operation"></a>MeasureAllZ 操作

名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


によって、レジスタの qubits が Pに評価されます。

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>説明

は、レジスタ全体のパリティを表すために、$Z/otimes z ~ otimes/cドット/otimes Z $ ベースで qubits のレジスタを測定します。

## <a name="input"></a>入力

### <a name="register--qubit"></a>register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

測定するレジスタ。



## <a name="output--__invalidresult__"></a>出力:__無効 <Result>__

$Z/otimes z/otimes-cドット/otimes Z $ の測定結果。