---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateCA
title: PrepareChoiStateCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateCA
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.
ms.openlocfilehash: abe75865149c985426a5eaf69cf41433829e1916
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210490"
---
# <a name="preparechoistateca-operation"></a>PrepareChoiStateCA 操作

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された参照およびターゲットレジスタに対し、制御されるバリアントと adjoint バリアントの両方を持つ特定の操作に対して、[Jamiołkowski] 状態を準備します。

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="op--qubit--unit--is-adj--ctl"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl




### <a name="reference--qubit"></a>参照: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [Microsoft... 準備した Istate](xref:Microsoft.Quantum.Preparation.PrepareChoiState)