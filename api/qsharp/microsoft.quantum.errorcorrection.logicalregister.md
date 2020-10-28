---
uid: Microsoft.Quantum.ErrorCorrection.LogicalRegister
title: LogicalRegister ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: LogicalRegister
qsharp.summary: Type for register of physical qubits `Qubit[]` that encode the logical qubits.
ms.openlocfilehash: 429b53d74ef7a0090a6f476656bb1d6cfaa23ade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712271"
---
# <a name="logicalregister-user-defined-type"></a>LogicalRegister ユーザー定義型

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


論理 qubits をエンコードする物理 qubits のレジスタの場合は、「」と入力 `Qubit[]` します。

```qsharp

newtype LogicalRegister = (Qubit[]);
```

