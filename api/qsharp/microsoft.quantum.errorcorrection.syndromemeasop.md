---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Syn% Memeasop ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 1314e16d26c7310bab21caa91cb398d4b6f09b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712117"
---
# <a name="syndromemeasop-user-defined-type"></a>Syn% Memeasop ユーザー定義型

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


エラー修正コードブロックのより隣人を測定するために使用される操作を表します。

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a>解説

このシグネチャは、 `(LogicalRegister => Syndrome)` の qubits と、補助 qubits `LogicalRegister` の後に補助 qubits の測定値を指定して、 `Syndrome` これらの測定値を表す値を抽出する操作を表し `Result[]` ます。

## <a name="see-also"></a>参照

- [Microsoft... ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [より隣人を修正します。](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)