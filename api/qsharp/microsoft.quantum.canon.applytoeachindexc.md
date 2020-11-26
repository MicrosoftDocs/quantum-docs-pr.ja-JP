---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Applytoindexc 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 38fa23c70965118f1787f156bd617d6e967aba05
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217664"
---
# <a name="applytoeachindexc-operation"></a>Applytoindexc 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


レジスタ内のインデックスが付けられた各要素に単一の qubit 演算を適用します。
修飾子は、 `C` single qubit 操作が制御可能であることを示します。

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a>入力

### <a name="singleelementoperation--intt--unit--is-ctl"></a>singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です

各 qubit に適用する操作。


### <a name="register--t"></a>register: t []

指定された操作を適用する qubits の配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

各操作が動作するターゲット。

## <a name="see-also"></a>参照

- [Microsoft...... のインデックス](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)