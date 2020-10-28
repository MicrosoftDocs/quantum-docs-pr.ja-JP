---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717591"
---
# <a name="applytoeach-operation"></a>ApplyToEach 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


レジスタ内の各要素に単一の qubit 演算を適用します。

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>入力

### <a name="singleelementoperation--t--unit"></a>singleElementOperation: t => [Unit](xref:microsoft.quantum.lang-ref.unit) 

各 qubit に適用する操作。


### <a name="register--t"></a>register: t []

指定された操作を適用する qubits の配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

操作が動作するターゲット。

## <a name="see-also"></a>参照

- [Microsoft................](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [Microsoft.......](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [Microsoft... の各 Ca](xref:Microsoft.Quantum.Canon.ApplyToEachCA)