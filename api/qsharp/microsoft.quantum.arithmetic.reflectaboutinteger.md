---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719714"
---
# <a name="reflectaboutinteger-operation"></a>ReflectAboutInteger 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


指定された古典的な整数に関するクォンタムレジスタを反映します。

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>説明

クォンタムレジスタが最初に state $ \ sum_i \ alpha_i \ket{i} $ に指定されている場合、各 $ \ket{i} $ は整数 $i $ を表す基礎状態であり、指定された整数 $ \ket{j} $、$ $ \ sum_i (-1) ^ {\ delta_ {ij}} \ alpha_i \ket{i} $ $ の基礎状態に関するレジスタの状態を反映します。

## <a name="input"></a>入力

### <a name="index--int"></a>index: [Int](xref:microsoft.quantum.lang-ref.int)

反映するベース状態のインデックスを作成する古典整数。


### <a name="reg--littleendian"></a>reg: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

この操作はインプレースで実装され、追加の補助 qubits が明示的に割り当てられることはありません。