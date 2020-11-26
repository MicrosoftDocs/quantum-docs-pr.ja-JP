---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: 各インデックス操作の Applytoa
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 746bc19f7a137ef476a25abdabc4737ed6727ff2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217614"
---
# <a name="applytoeachindex-operation"></a>各インデックス操作の Applytoa

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


レジスタ内のインデックスが付けられた各要素に単一の qubit 演算を適用します。

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>入力

### <a name="singleelementoperation--intt--unit"></a>singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), t) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

各 qubit に適用する操作。


### <a name="register--t"></a>register: t []

指定された操作を適用する qubits の配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

各操作が動作するターゲット。

## <a name="see-also"></a>参照

- [Microsoft. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [Microsoft.....。](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [Microsoft.....。](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [Microsoft........ の Indexca](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)