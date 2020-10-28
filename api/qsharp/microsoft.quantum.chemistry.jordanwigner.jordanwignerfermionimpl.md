---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionImpl
title: JordanWignerFermionImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 616174d4d7f5ac8f4cea9454098d819468076648
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714007"
---
# <a name="jordanwignerfermionimpl-operation"></a><span data-ttu-id="62ac2-102">JordanWignerFermionImpl 操作</span><span class="sxs-lookup"><span data-stu-id="62ac2-102">JordanWignerFermionImpl operation</span></span>

<span data-ttu-id="62ac2-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="62ac2-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="62ac2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62ac2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="62ac2-105">Dynamical generator を simulatable ゲートと JordanWigner ベースの拡張のセットとして表します。</span><span class="sxs-lookup"><span data-stu-id="62ac2-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

<span data-ttu-id="62ac2-106">詳細については、「 [Dynamical Generator モデリング](../libraries/data-structures#dynamical-generator-modeling) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62ac2-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation JordanWignerFermionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="62ac2-107">入力</span><span class="sxs-lookup"><span data-stu-id="62ac2-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="62ac2-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="62ac2-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="62ac2-109">JordanWigner での、ユニタリの発展として表現されるジェネレーターインデックス。</span><span class="sxs-lookup"><span data-stu-id="62ac2-109">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="62ac2-110">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="62ac2-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="62ac2-111">で参照されている用語による時間の推移の期間に対する乗数 `generatorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="62ac2-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="62ac2-112">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="62ac2-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="62ac2-113">時間進化演算子による登録が行われます。</span><span class="sxs-lookup"><span data-stu-id="62ac2-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="62ac2-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62ac2-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

