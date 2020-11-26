---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217868"
---
# <a name="applytoeach-operation"></a>ApplyToEach 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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