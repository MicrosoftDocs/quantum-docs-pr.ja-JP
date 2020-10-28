---
uid: Microsoft.Quantum.Simulation.Unitary
title: ユーザー定義型 (ユニタリ)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: d2bba42e80132d0879f42922f28ad50bef54edf3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725332"
---
# <a name="unitary-user-defined-type"></a>ユーザー定義型 (ユニタリ)

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


は、ユニタリ演算子での進化を表します。

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```

