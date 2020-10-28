---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterCA
title: RestrictedToSubregisterCA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterCA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: e81193a85451b72a69a595fa81a9fb07f3038c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715528"
---
# <a name="restrictedtosubregisterca-function"></a>RestrictedToSubregisterCA 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


操作をレジスタのインデックスの配列 (サブレジスタ) に制限します。
修飾子は、 `CA` 操作が制御可能であり、adjointable であることを示します。

```qsharp
function RestrictedToSubregisterCA (op : (Qubit[] => Unit is Adj + Ctl), idxs : Int[]) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>入力

### <a name="op--qubit--unit-adj--ctl"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl

サブレジスタに限定される操作。


### <a name="idxs--int"></a>idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]

インデックスの配列。操作が制限される qubits を示します。



## <a name="output--qubit--unit-adj--ctl"></a>出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl



## <a name="see-also"></a>参照

- [Microsoft. RestrictedToSubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)