---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: a16d7405388b560edcdb6c36b6668791f7ba1398
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725001"
---
# <a name="mresetx-operation"></a>MResetX 操作

名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)

パック [](https://nuget.org/packages/)


X ベースの1つの qubit を測定し、測定値に従って固定の初期状態にリセットします。

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a>説明

$X $ 単位で1つの qubit 測定を実行し、測定値に従って qubit が $ \ket $ に返されることを確認し {0} ます。

## <a name="input"></a>入力

### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

測定される1つの qubit。



## <a name="output--__invalidresult__"></a>出力: __無効 <Result>__

`target`P# li $X $ ベースで測定した結果。