---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 8a3557f76d5d7a7b6375e5640cf6d11172cd38a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723470"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="4f3ce-102">LocalRotationsLayer 関数</span><span class="sxs-lookup"><span data-stu-id="4f3ce-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="4f3ce-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4f3ce-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4f3ce-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4f3ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4f3ce-105">指定された軸に沿って非制御 (単 qubit) の回転の配列を返します。レジスタ内の qubit ごとに1つの回転があり、個別のモデルパラメーターによってパラメーター化されます。</span><span class="sxs-lookup"><span data-stu-id="4f3ce-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="4f3ce-106">入力</span><span class="sxs-lookup"><span data-stu-id="4f3ce-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="4f3ce-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f3ce-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4f3ce-108">指定したレイヤーによって操作された qubits の数。</span><span class="sxs-lookup"><span data-stu-id="4f3ce-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="4f3ce-109">axis: [P# li](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="4f3ce-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="4f3ce-110">指定されたレイヤー内の各回転の回転軸。</span><span class="sxs-lookup"><span data-stu-id="4f3ce-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="4f3ce-111">出力: [Controlle入力](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="4f3ce-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="4f3ce-112">指定された軸についての制御された回転の配列 (各 qubits に1つ) `nQubits` 。</span><span class="sxs-lookup"><span data-stu-id="4f3ce-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>