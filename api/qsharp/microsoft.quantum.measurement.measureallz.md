---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711076"
---
# <a name="measureallz-operation"></a>MeasureAllZ 操作

名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)

パック [](https://nuget.org/packages/)


によって、レジスタの qubits が Pに評価されます。

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>説明

は、レジスタ全体のパリティを表すために、$Z/otimes z ~ otimes/cドット/otimes Z $ ベースで qubits のレジスタを測定します。

## <a name="input"></a>入力

### <a name="register--qubit"></a>register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

測定するレジスタ。



## <a name="output--__invalidresult__"></a>出力: __無効 <Result>__

$Z/otimes z/otimes-cドット/otimes Z $ の測定結果。