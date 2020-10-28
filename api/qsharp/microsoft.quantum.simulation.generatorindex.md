---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 8d36f74fbf122469e9e829b950e4ed9a6e3a35a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723904"
---
# <a name="generatorindex-user-defined-type"></a>GeneratorIndex ユーザー定義型

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


すべての dynamical ジェネレーター (Hermitian 演算子など) のセットに含まれる1つのプリミティブ用語を表します。これは、を通じてジェネレーターによる時間の進化にジェネレーターからのマップが存在します。 `EvolutionSet`

最初の要素 (Int [], Double []) は、1つの用語にインデックスが付けられています。たとえば、P# li 文字列の場合は、係数0.5 を使用して、([1, 1, 2], [0.5]) によってインデックスが作成されます。 また、X cos φ + Y sin φなど、連続変数によってパラメーター化された Hamiltonians は、インスタンスを ([], [φ]) で表すことができます。 2番目の要素は、ジェネレーターが動作するサブシステムのインデックスを生成します。

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a>解説

> [!WARNING]
> の解釈は、 `GeneratorIndex` 特定のジェネレーターセットへの参照とは異なり、定義されていません。

## <a name="see-also"></a>参照

- [EvolutionSet です。](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [PauliEvolutionSet です。](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)