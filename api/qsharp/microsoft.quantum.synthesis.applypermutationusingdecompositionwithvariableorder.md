---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 1edbc0a2948fdf3ae67f14b3c552676feaa7f498
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725295"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a>ApplyPermutationUsingDecompositionWithVariableOrder 操作

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パック [](https://nuget.org/packages/)


分解ベースの合成を使用する順列を指定して、クォンタムの状態の振幅を Permutes します。

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>説明

この操作は、変数の順序を指定できるのより一般的なバージョンです @"microsoft.quantum.synthesis.applypermutationusingdecomposition" 。 変数の順序が異なると、制御ゲートに使用される分解シーケンスと真理テーブルが変更され @"microsoft.quantum.intrinsic.x" ます。  したがって、変数の順序を変更すると、順列を実現するために使用されるゲート全体の数が変わります。

## <a name="input"></a>入力

### <a name="perm--int"></a>perm: [Int](xref:microsoft.quantum.lang-ref.int)[]

0から始まる $ 2 ^ n $ 要素の順列。


### <a name="variableorder--int"></a>変数の順序: [Int](xref:microsoft.quantum.lang-ref.int)[]

0から始まる $ elements $n の順列。


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

順列が適用される $n $ qubits の一覧。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [ApplyPermutationUsingDecomposition です。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [ApplyPermutationUsingTransformation です。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)