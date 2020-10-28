---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a8b599035de6fede10bdaf8cef17f2124a59f064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715542"
---
# <a name="restrictedtosubregister-function"></a>RestrictedToSubregister 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


操作をレジスタのインデックスの配列 (サブレジスタ) に制限します。

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a>入力

### <a name="op--qubit--unit"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

サブレジスタに限定される操作。


### <a name="idxs--int"></a>idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]

インデックスの配列。操作が制限される qubits を示します。



## <a name="output--qubit--unit"></a>出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 



## <a name="see-also"></a>参照

- [Microsoft. RestrictedToSubregisterA](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [Microsoft. RestrictedToSubregisterC](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [Microsoft. RestrictedToSubregisterCA](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)