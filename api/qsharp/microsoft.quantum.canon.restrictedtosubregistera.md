---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: RestrictedToSubregisterA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: d45c43caed35df8fb89d9d38e540faf5a21ea064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715533"
---
# <a name="restrictedtosubregistera-function"></a>RestrictedToSubregisterA 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


操作をレジスタのインデックスの配列 (サブレジスタ) に制限します。
修飾子は、 `A` 操作が adjointable であることを示します。

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a>入力

### <a name="op--qubit--unit-adj"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

サブレジスタに限定される操作。


### <a name="idxs--int"></a>idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]

インデックスの配列。操作が制限される qubits を示します。



## <a name="output--qubit--unit-adj"></a>出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞



## <a name="see-also"></a>参照

- [Microsoft. RestrictedToSubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)