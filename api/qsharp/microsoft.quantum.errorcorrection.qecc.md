---
uid: Microsoft.Quantum.ErrorCorrection.QECC
title: QECC ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: QECC
qsharp.summary: Represents an error-correcting code as defined by its encoder, decoder, and syndrome measurement procedure.
ms.openlocfilehash: 6a00875f53928da4e0b8da6a3e32e37a551a56b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712252"
---
# <a name="qecc-user-defined-type"></a>QECC ユーザー定義型

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


エンコーダー、デコーダー、およびより隣人測定手順によって定義された、エラー修正コードを表します。

```qsharp

newtype QECC = (Microsoft.Quantum.ErrorCorrection.EncodeOp, Microsoft.Quantum.ErrorCorrection.DecodeOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp);
```

