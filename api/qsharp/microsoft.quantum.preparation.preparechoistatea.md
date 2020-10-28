---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateA
title: Istatea 操作の実行
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateA
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with an adjoint variant onto given reference and target registers.
ms.openlocfilehash: c679f9a02aa15f9a582257770b8dc57d798d1b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710983"
---
# <a name="preparechoistatea-operation"></a>Istatea 操作の実行

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パック [](https://nuget.org/packages/)


指定された参照およびターゲットレジスタに adjoint バリアントを使用して、指定された操作に対して Jamiłkowski 状態を準備します。

```qsharp
operation PrepareChoiStateA (op : (Qubit[] => Unit is Adj), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="op--qubit--unit-adj"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞




### <a name="reference--qubit"></a>参照: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [Microsoft... 準備した Istate](xref:Microsoft.Quantum.Preparation.PrepareChoiState)