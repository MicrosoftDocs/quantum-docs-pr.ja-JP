---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateC
title: Istatec 操作の実行
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateC
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with a controlled variant onto given reference and target registers.
ms.openlocfilehash: b23b22fa4bf21ca48076ccda0db62b313f887aa9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724898"
---
# <a name="preparechoistatec-operation"></a>Istatec 操作の実行

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パック [](https://nuget.org/packages/)


指定された参照およびターゲットレジスタに制御されるバリアントを持つ特定の操作に対して、[Jamiłkowski] 状態を準備します。

```qsharp
operation PrepareChoiStateC (op : (Qubit[] => Unit is Ctl), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="op--qubit--unit-ctl"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl




### <a name="reference--qubit"></a>参照: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [Microsoft... 準備した Istate](xref:Microsoft.Quantum.Preparation.PrepareChoiState)