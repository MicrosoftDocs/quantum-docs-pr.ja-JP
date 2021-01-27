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
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="52a44-102">GeneratorIndex ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="52a44-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="52a44-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="52a44-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="52a44-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52a44-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52a44-105">すべての dynamical ジェネレーター (Hermitian 演算子など) のセットに含まれる1つのプリミティブ用語を表します。これは、を通じてジェネレーターによる時間の進化にジェネレーターからのマップが存在します。 `EvolutionSet`</span><span class="sxs-lookup"><span data-stu-id="52a44-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="52a44-106">最初の要素 (Int [], Double []) は、1つの用語にインデックスが付けられています。たとえば、P# li 文字列の場合は、係数0.5 を使用して、([1, 1, 2], [0.5]) によってインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="52a44-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="52a44-107">また、X cos φ + Y sin φなど、連続変数によってパラメーター化された Hamiltonians は、インスタンスを ([], [φ]) で表すことができます。</span><span class="sxs-lookup"><span data-stu-id="52a44-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="52a44-108">2番目の要素は、ジェネレーターが動作するサブシステムのインデックスを生成します。</span><span class="sxs-lookup"><span data-stu-id="52a44-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a><span data-ttu-id="52a44-109">例</span><span class="sxs-lookup"><span data-stu-id="52a44-109">Example</span></span>

<span data-ttu-id="52a44-110">を使用する  <xref:microsoft.quantum.simulation.paulievolutionset> と、$ \ pi X_2 X_5 Y_9 $ は次のように表されます。</span><span class="sxs-lookup"><span data-stu-id="52a44-110">Using  <xref:microsoft.quantum.simulation.paulievolutionset>, the operator $\pi X_2 X_5 Y_9$ is represented as:</span></span>

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a><span data-ttu-id="52a44-111">解説</span><span class="sxs-lookup"><span data-stu-id="52a44-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="52a44-112">の解釈は、 `GeneratorIndex` 特定のジェネレーターセットへの参照とは異なり、定義されていません。</span><span class="sxs-lookup"><span data-stu-id="52a44-112">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="52a44-113">参照</span><span class="sxs-lookup"><span data-stu-id="52a44-113">See Also</span></span>

- [<span data-ttu-id="52a44-114">EvolutionSet です。</span><span class="sxs-lookup"><span data-stu-id="52a44-114">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="52a44-115">PauliEvolutionSet です。</span><span class="sxs-lookup"><span data-stu-id="52a44-115">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)