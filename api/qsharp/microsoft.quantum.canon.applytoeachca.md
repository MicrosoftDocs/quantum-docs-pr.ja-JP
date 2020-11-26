---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: 各 Ca 操作の適用
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: dcfd4619a77413e71044e6a7d5fc19a9f22bbf94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217749"
---
# <a name="applytoeachca-operation"></a>各 Ca 操作の適用

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


レジスタ内の各要素に単一の qubit 演算を適用します。
修飾子は、 `CA` single qubit 操作が制御可能で adjointable であることを示します。

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a>singleElementOperation: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

各 qubit に適用する操作。


### <a name="register--t"></a>register: t []

指定された操作を適用する qubits の配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

操作が動作するターゲット。

## <a name="see-also"></a>参照

- [Microsoft. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)