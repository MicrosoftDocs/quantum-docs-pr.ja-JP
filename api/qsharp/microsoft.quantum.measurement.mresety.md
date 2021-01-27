---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 2e41e76a46b68178a8a22b39131d6ca2a8c50b64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854632"
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