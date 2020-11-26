---
uid: Microsoft.Quantum.Intrinsic.Reset
title: リセット操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: 61b5e4ccdf009dcb6c639e3d8e23bc73a6e475b5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198675"
---
# <a name="reset-operation"></a>リセット操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


1つの qubit を指定すると、それを測定し、安全に解放できるように、それが | 0 ⟩状態であることを確認します。

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

状態が $ \ket $ にリセットされる qubit {0} 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

