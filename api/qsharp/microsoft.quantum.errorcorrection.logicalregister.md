---
uid: Microsoft.Quantum.ErrorCorrection.LogicalRegister
title: LogicalRegister ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: LogicalRegister
qsharp.summary: Type for register of physical qubits `Qubit[]` that encode the logical qubits.
ms.openlocfilehash: 96fb567814e69060707a8080749e23883ae2a860
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825875"
---
# <a name="logicalregister-user-defined-type"></a>LogicalRegister ユーザー定義型

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


論理 qubits をエンコードする物理 qubits のレジスタの場合は、「」と入力 `Qubit[]` します。

```qsharp

newtype LogicalRegister = (Qubit[]);
```

