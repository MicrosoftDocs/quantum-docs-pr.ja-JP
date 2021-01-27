---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: be820c87ee19230713d6c3e5681bbe3678040e95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850483"
---
# <a name="applytosubregister-operation"></a>ApplyToSubregister 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


インデックスの配列によって指定された qubits を使用して、レジスタのサブレジスタに操作を適用します。

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="op--qubit--unit"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Subregister に適用する操作です。


### <a name="idxs--int"></a>idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]

操作が適用される qubits を示すインデックスの配列。


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

操作が動作する登録です。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>例

次の3つの qubit 状態を作成します。 $ \ frac {1} {\ sqrt {2} } \ket {0} \_ 2 (\ket {0} \_ 1 \ k ( {0} 3 + \ket {1} \_ 1 \ k {1} ) $:

```qsharp
    using (register = Qubit[3]) {
        ApplyToSubregister(Exp([PauliX,PauliY],PI() / 4.0,_), [1,3], register);
    }
```

## <a name="see-also"></a>参照

- [Microsoft. ApplyToSubregisterA](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [Microsoft. Canon. ApplyToSubregisterC](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [Microsoft. Canon. ApplyToSubregisterCA](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)