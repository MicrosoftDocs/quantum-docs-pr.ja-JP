---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: fc9ba6576b56d7df1a57334e1da46b9c48376ecb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853738"
---
# <a name="mresetz-operation"></a>MResetZ 操作

名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


1つの qubit を Z ベースで測定し、測定値に従って固定の初期状態にリセットします。

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a>説明

$Z $ 単位で1つの qubit 測定を実行し、測定値に従って qubit が $ \ket $ に返されることを確認し {0} ます。

## <a name="input"></a>入力

### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

測定される1つの qubit。



## <a name="output--__invalidresult__"></a>出力:__無効 <Result>__

`target`P# li $Z $ ベースで測定した結果。