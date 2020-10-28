---
uid: Microsoft.Quantum.Intrinsic.Reset
title: リセット操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: c89cbbce49e294e56abc11b3b0492d2ed8e980a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720871"
---
# <a name="reset-operation"></a>リセット操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

パック [](https://nuget.org/packages/)


1つの qubit を指定すると、それを測定し、安全に解放できるように、それが | 0 ⟩状態であることを確認します。

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

状態が $ \ket $ にリセットされる qubit {0} 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

