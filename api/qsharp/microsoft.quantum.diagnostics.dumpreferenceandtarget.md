---
uid: Microsoft.Quantum.Diagnostics.DumpReferenceAndTarget
title: DumpReferenceAndTarget 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpReferenceAndTarget
qsharp.summary: Uses DumpRegister to provide diagnostics on the state of a reference and target register. Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.
ms.openlocfilehash: f791f6f1e3c1b1da14ac3548a4bd78bb4f24ff83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712854"
---
# <a name="dumpreferenceandtarget-operation"></a>DumpReferenceAndTarget 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


DumpRegister を使用して、参照およびターゲットレジスタの状態に関する診断を提供します。 1つの結合レジスタとしてではなく、個別のレジスタとしてオーバーライドおよび解釈できるようにするために、個別の操作として記述されます。

```qsharp
operation DumpReferenceAndTarget (reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="reference--qubit"></a>参照: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

