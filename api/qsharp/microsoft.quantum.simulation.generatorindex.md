---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 762dac81ea0963443f0338cea1b879856c84b0ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858377"
---
# <a name="generatorindex-user-defined-type"></a>GeneratorIndex ユーザー定義型

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


すべての dynamical ジェネレーター (Hermitian 演算子など) のセットに含まれる1つのプリミティブ用語を表します。これは、を通じてジェネレーターによる時間の進化にジェネレーターからのマップが存在します。 `EvolutionSet`

最初の要素 (Int [], Double []) は、1つの用語にインデックスが付けられています。たとえば、P# li 文字列の場合は、係数0.5 を使用して、([1, 1, 2], [0.5]) によってインデックスが作成されます。 また、X cos φ + Y sin φなど、連続変数によってパラメーター化された Hamiltonians は、インスタンスを ([], [φ]) で表すことができます。 2番目の要素は、ジェネレーターが動作するサブシステムのインデックスを生成します。

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a>例

を使用する  <xref:microsoft.quantum.simulation.paulievolutionset> と、$ \ pi X_2 X_5 Y_9 $ は次のように表されます。

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a>解説

> [!WARNING]
> の解釈は、 `GeneratorIndex` 特定のジェネレーターセットへの参照とは異なり、定義されていません。

## <a name="see-also"></a>参照

- [EvolutionSet です。](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [PauliEvolutionSet です。](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)