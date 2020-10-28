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
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="778c1-102">GeneratorIndex ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="778c1-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="778c1-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="778c1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="778c1-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="778c1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="778c1-105">すべての dynamical ジェネレーター (Hermitian 演算子など) のセットに含まれる1つのプリミティブ用語を表します。これは、を通じてジェネレーターによる時間の進化にジェネレーターからのマップが存在します。 `EvolutionSet`</span><span class="sxs-lookup"><span data-stu-id="778c1-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="778c1-106">最初の要素 (Int [], Double []) は、1つの用語にインデックスが付けられています。たとえば、P# li 文字列の場合は、係数0.5 を使用して、([1, 1, 2], [0.5]) によってインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="778c1-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="778c1-107">また、X cos φ + Y sin φなど、連続変数によってパラメーター化された Hamiltonians は、インスタンスを ([], [φ]) で表すことができます。</span><span class="sxs-lookup"><span data-stu-id="778c1-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="778c1-108">2番目の要素は、ジェネレーターが動作するサブシステムのインデックスを生成します。</span><span class="sxs-lookup"><span data-stu-id="778c1-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a><span data-ttu-id="778c1-109">解説</span><span class="sxs-lookup"><span data-stu-id="778c1-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="778c1-110">の解釈は、 `GeneratorIndex` 特定のジェネレーターセットへの参照とは異なり、定義されていません。</span><span class="sxs-lookup"><span data-stu-id="778c1-110">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="778c1-111">参照</span><span class="sxs-lookup"><span data-stu-id="778c1-111">See Also</span></span>

- [<span data-ttu-id="778c1-112">EvolutionSet です。</span><span class="sxs-lookup"><span data-stu-id="778c1-112">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="778c1-113">PauliEvolutionSet です。</span><span class="sxs-lookup"><span data-stu-id="778c1-113">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)