---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 2333dcbd2988480e2b2b9b217b26705f3578de00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230533"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="9e396-102">IntsToPaulis 関数</span><span class="sxs-lookup"><span data-stu-id="9e396-102">IntsToPaulis function</span></span>

<span data-ttu-id="9e396-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9e396-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9e396-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9e396-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9e396-105">整数の配列をシングル qubit の演算子の配列に変換します。</span><span class="sxs-lookup"><span data-stu-id="9e396-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="9e396-106">入力</span><span class="sxs-lookup"><span data-stu-id="9e396-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="9e396-107">Int: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9e396-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9e396-108">`0..3`P# li 演算子に変換される範囲内の整数の配列。</span><span class="sxs-lookup"><span data-stu-id="9e396-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="9e396-109">出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="9e396-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="9e396-110">`paulis` `Pauli[]` `ints` `paulis[idxPauli]` `[PauliI, PauliX, PauliY, PauliZ]` によって指定されたの要素と同じ長さの、p# li 演算子の配列 `ints[idxPauli]` 。</span><span class="sxs-lookup"><span data-stu-id="9e396-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>