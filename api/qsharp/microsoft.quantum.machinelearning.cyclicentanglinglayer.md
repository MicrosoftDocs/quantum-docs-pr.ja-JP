---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720511"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="b741d-102">CyclicEntanglingLayer 関数</span><span class="sxs-lookup"><span data-stu-id="b741d-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="b741d-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b741d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b741d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b741d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b741d-105">指定された軸に沿って1つの制御された回転の配列を返します。 qubits のレジスタで周期的に配置され、個別のモデルパラメーターによってパラメーター化されます。</span><span class="sxs-lookup"><span data-stu-id="b741d-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="b741d-106">入力</span><span class="sxs-lookup"><span data-stu-id="b741d-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="b741d-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b741d-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b741d-108">指定したレイヤーによって操作された qubits の数。</span><span class="sxs-lookup"><span data-stu-id="b741d-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="b741d-109">axis: [P# li](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="b741d-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="b741d-110">指定されたレイヤー内の各回転の回転軸。</span><span class="sxs-lookup"><span data-stu-id="b741d-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="b741d-111">stride: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b741d-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b741d-112">各回転のターゲットと制御のインデックスを分離する。</span><span class="sxs-lookup"><span data-stu-id="b741d-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="b741d-113">出力: [Controlle入力](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="b741d-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="b741d-114">Qubit のレジスタ間で周期的に配置された、2つの qubit 制御された回転の配列 `nQubits` 。</span><span class="sxs-lookup"><span data-stu-id="b741d-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>