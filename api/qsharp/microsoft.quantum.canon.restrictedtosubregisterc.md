---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: RestrictedToSubregisterC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2ca32cf8c85f33f498a30f71833b3dd69db6da6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715514"
---
# <a name="restrictedtosubregisterc-function"></a>RestrictedToSubregisterC 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


操作をレジスタのインデックスの配列 (サブレジスタ) に制限します。
修飾子は、 `C` 操作が制御可能であることを示します。

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a>入力

### <a name="op--qubit--unit-ctl"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl

サブレジスタに限定される操作。


### <a name="idxs--int"></a>idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]

インデックスの配列。操作が制限される qubits を示します。



## <a name="output--qubit--unit-ctl"></a>出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl



## <a name="see-also"></a>参照

- [Microsoft. RestrictedToSubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)