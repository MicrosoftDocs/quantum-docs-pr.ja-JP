---
uid: Microsoft.Quantum.Simulation.Unitary
title: ユーザー定義型 (ユニタリ)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: c34d84fb5f319c285356b284bd1f1c18ec64ef46
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192147"
---
# <a name="unitary-user-defined-type"></a>ユーザー定義型 (ユニタリ)

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


は、ユニタリ演算子での進化を表します。

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```

