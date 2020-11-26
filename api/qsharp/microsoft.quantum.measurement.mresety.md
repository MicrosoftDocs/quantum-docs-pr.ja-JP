---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 36c6f227135b5ccaf1146fd7afdc8205d416c5dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227031"
---
# <a name="mresety-operation"></a>MResetY 操作

名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


Y 単位で1つの qubit を測定し、測定値に従って固定の初期状態にリセットします。

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a>説明

$Y $ 単位で1つの qubit 測定を実行し、測定値に従って qubit が $ \ket $ に返されることを確認し {0} ます。

## <a name="input"></a>入力

### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

測定される1つの qubit。



## <a name="output--__invalidresult__"></a>出力:__無効 <Result>__

`target`P# li $Y $ ベースで測定した結果。