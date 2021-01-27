---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionImpl
title: JordanWignerFermionImpl 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 5b975457803b8978d846bcd3c8256dfacdb90bee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98838184"
---
# <a name="jordanwignerfermionimpl-operation"></a><span data-ttu-id="aaee3-102">JordanWignerFermionImpl 操作</span><span class="sxs-lookup"><span data-stu-id="aaee3-102">JordanWignerFermionImpl operation</span></span>

<span data-ttu-id="aaee3-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="aaee3-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="aaee3-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="aaee3-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="aaee3-105">Dynamical generator を simulatable ゲートと JordanWigner ベースの拡張のセットとして表します。</span><span class="sxs-lookup"><span data-stu-id="aaee3-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

<span data-ttu-id="aaee3-106">詳細については、「 [Dynamical Generator モデリング](../libraries/data-structures#dynamical-generator-modeling) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaee3-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation JordanWignerFermionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="aaee3-107">入力</span><span class="sxs-lookup"><span data-stu-id="aaee3-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="aaee3-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="aaee3-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="aaee3-109">JordanWigner での、ユニタリの発展として表現されるジェネレーターインデックス。</span><span class="sxs-lookup"><span data-stu-id="aaee3-109">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="aaee3-110">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aaee3-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aaee3-111">で参照されている用語による時間の推移の期間に対する乗数 `generatorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="aaee3-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="aaee3-112">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aaee3-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aaee3-113">時間進化演算子による登録が行われます。</span><span class="sxs-lookup"><span data-stu-id="aaee3-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aaee3-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aaee3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

