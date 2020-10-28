---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724674"
---
# <a name="settobasisstate-operation"></a>SetToBasisState 操作

名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)

パック [](https://nuget.org/packages/)


Qubit を測定し、必要に応じてビットフリップを適用することによって、指定された計算基準の状態に qubit を設定します。

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="desired--__invalidresult__"></a>目的: __無効 <Result>__

Qubit を設定する基準の状態。


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

状態が設定される qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

この操作の不変性として、の直後にを呼び出すと、 `M(q)` `SetToBasisState(result, q)` が返され `result` ます。