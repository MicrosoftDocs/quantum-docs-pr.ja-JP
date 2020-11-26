---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ade0640b07f633982e98d5d02239fa205909bcce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196244"
---
# <a name="partialrotationslayer-function"></a><span data-ttu-id="d9179-102">PartialRotationsLayer 関数</span><span class="sxs-lookup"><span data-stu-id="d9179-102">PartialRotationsLayer function</span></span>

<span data-ttu-id="d9179-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d9179-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d9179-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d9179-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d9179-105">個別のモデルパラメーターによってパラメーター化された、指定した軸に沿った単一の qubit 回転の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="d9179-105">Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.</span></span>

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="d9179-106">入力</span><span class="sxs-lookup"><span data-stu-id="d9179-106">Input</span></span>

### <a name="idxsqubits--int"></a><span data-ttu-id="d9179-107">idxsQubits: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d9179-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d9179-108">各回転のターゲットとして使用される qubits のインデックス。</span><span class="sxs-lookup"><span data-stu-id="d9179-108">Indices for the qubits to be used as the targets for each rotation.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="d9179-109">axis: [P# li](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="d9179-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="d9179-110">指定されたレイヤー内の各回転の回転軸。</span><span class="sxs-lookup"><span data-stu-id="d9179-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="d9179-111">出力: [Controlle入力](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="d9179-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="d9179-112">指定された軸についての制御された回転の配列 (各 qubits に1つ) `nQubits` 。</span><span class="sxs-lookup"><span data-stu-id="d9179-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>