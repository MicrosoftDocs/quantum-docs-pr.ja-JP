---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: ブール関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713601"
---
# <a name="boolarrayaspauli-function"></a>ブール関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パック [](https://nuget.org/packages/)


ビット文字列を指定した場合は、single qubit の演算子の配列として表されるマルチ qubit の P# li 演算子を返します。

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a>入力

### <a name="pauli--pauli"></a>p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li

Qubits where に適用する p# li 演算子 `bitsApply == bits[idx]` 。


### <a name="bitapply--bool"></a>bitApply: [Bool](xref:microsoft.quantum.lang-ref.bool)

bit がこの値の場合は、P# li を適用します。


### <a name="bits--bool"></a>bits: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

ブール型の配列。



## <a name="output--pauli"></a>出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]



## <a name="remarks"></a>解説

ブール型の配列とクォンタムレジスタは同じ長さである必要があります。