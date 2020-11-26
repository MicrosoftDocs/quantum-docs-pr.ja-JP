---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Applytoall Indexca 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: abb616498a8ff9c3348df81cf0ca1a1669561eec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208943"
---
# <a name="applytoeachindexca-operation"></a>Applytoall Indexca 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


レジスタ内のインデックスが付けられた各要素に単一の qubit 演算を適用します。
修飾子は、 `CA` single qubit 操作が adjointable で制御可能であることを示します。

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a>singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

各 qubit に適用する操作。


### <a name="register--t"></a>register: t []

指定された操作を適用する qubits の配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

各操作が動作するターゲット。

## <a name="see-also"></a>参照

- [Microsoft...... のインデックス](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)