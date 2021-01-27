---
uid: Microsoft.Quantum.Intrinsic.Reset
title: リセット操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: b4275796b966bfe7f55271f4e92866410a14e830
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818641"
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

