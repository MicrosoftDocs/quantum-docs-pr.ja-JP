---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: PauliEvolutionImpl 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 868f3eef187e8e993127cfcab21e1574583ac845
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229139"
---
# <a name="paulievolutionimpl-operation"></a><span data-ttu-id="1e6e6-102">PauliEvolutionImpl 操作</span><span class="sxs-lookup"><span data-stu-id="1e6e6-102">PauliEvolutionImpl operation</span></span>

<span data-ttu-id="1e6e6-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1e6e6-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1e6e6-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e6e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e6e6-105">Dynamical generator を simulatable ゲートのセットとして表し、拡張を p にします。</span><span class="sxs-lookup"><span data-stu-id="1e6e6-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

<span data-ttu-id="1e6e6-106">詳細については、「 [Dynamical Generator モデリング](/quantum/libraries/data-structures#dynamical-generator-modeling) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e6e6-106">See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1e6e6-107">入力</span><span class="sxs-lookup"><span data-stu-id="1e6e6-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="1e6e6-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="1e6e6-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="1e6e6-109">生成された周期的な展開で表されるジェネレーターインデックス。</span><span class="sxs-lookup"><span data-stu-id="1e6e6-109">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>


### <a name="delta--double"></a><span data-ttu-id="1e6e6-110">デルタ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1e6e6-110">delta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1e6e6-111">で参照されている用語による時間の推移の期間に対する乗数 `generatorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="1e6e6-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1e6e6-112">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1e6e6-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1e6e6-113">時間進化演算子による登録が行われます。</span><span class="sxs-lookup"><span data-stu-id="1e6e6-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e6e6-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e6e6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

