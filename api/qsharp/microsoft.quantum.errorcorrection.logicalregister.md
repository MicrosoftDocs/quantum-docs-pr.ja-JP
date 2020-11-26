---
uid: Microsoft.Quantum.ErrorCorrection.LogicalRegister
title: LogicalRegister ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: LogicalRegister
qsharp.summary: Type for register of physical qubits `Qubit[]` that encode the logical qubits.
ms.openlocfilehash: 3847d80c66200925758edafdc0efbd04dc2f82df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200715"
---
# <a name="logicalregister-user-defined-type"></a>LogicalRegister ユーザー定義型

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


論理 qubits をエンコードする物理 qubits のレジスタの場合は、「」と入力 `Qubit[]` します。

```qsharp

newtype LogicalRegister = (Qubit[]);
```

