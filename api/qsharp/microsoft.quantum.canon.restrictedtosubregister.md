---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: c5a6bbe16d2f6a317f6ed6f258077095465995f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840229"
---
# <a name="restrictedtosubregister-function"></a>RestrictedToSubregister 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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