---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: 各インデックス操作の Applytoa
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 8b34dc24580a3df7ae2c13ef87a6fa10c7afd3f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844593"
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