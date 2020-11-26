---
uid: Microsoft.Quantum.Intrinsic.T
title: T 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 352ef2c1b15a46dea85c420fc6f1cfab0382e73a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198403"
---
# <a name="t-operation"></a>T 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


T ゲートを1つの qubit に適用します。

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

この操作は、ユニタリ行列 \begin{align} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \ pi/4} \end{bmatrix}. でシミュレートできます。
\end{align}

## <a name="input"></a>入力

### <a name="qubit--qubit"></a>qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

ゲートを適用する qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

