---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorImpl
title: _JordanWignerClusterOperatorImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 9507558ebe73bce87d9089aad22b94c1d9d579d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714604"
---
# <a name="_jordanwignerclusteroperatorimpl-operation"></a><span data-ttu-id="2a4dd-102">_JordanWignerClusterOperatorImpl 操作</span><span class="sxs-lookup"><span data-stu-id="2a4dd-102">_JordanWignerClusterOperatorImpl operation</span></span>

<span data-ttu-id="2a4dd-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="2a4dd-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="2a4dd-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a4dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a4dd-105">Dynamical generator を simulatable ゲートと JordanWigner ベースの拡張のセットとして表します。</span><span class="sxs-lookup"><span data-stu-id="2a4dd-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

<span data-ttu-id="2a4dd-106">詳細については、「 [Dynamical Generator モデリング](../libraries/data-structures#dynamical-generator-modeling) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a4dd-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JordanWignerClusterOperatorImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2a4dd-107">入力</span><span class="sxs-lookup"><span data-stu-id="2a4dd-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="2a4dd-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2a4dd-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="2a4dd-109">JordanWigner での、ユニタリの発展として表現されるジェネレーターインデックス。</span><span class="sxs-lookup"><span data-stu-id="2a4dd-109">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="2a4dd-110">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2a4dd-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2a4dd-111">シミュレーションアルゴリズムの署名に一致するダミー変数。</span><span class="sxs-lookup"><span data-stu-id="2a4dd-111">Dummy variable to match signature of simulation algorithms.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2a4dd-112">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2a4dd-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2a4dd-113">時間進化演算子による登録が行われます。</span><span class="sxs-lookup"><span data-stu-id="2a4dd-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2a4dd-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a4dd-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

