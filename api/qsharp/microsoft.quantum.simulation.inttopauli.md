---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: Inttop/Li 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229207"
---
# <a name="inttopauli-function"></a><span data-ttu-id="e0cec-102">Inttop/Li 関数</span><span class="sxs-lookup"><span data-stu-id="e0cec-102">IntToPauli function</span></span>

<span data-ttu-id="e0cec-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e0cec-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e0cec-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0cec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0cec-105">整数をシングル qubit の P# li 演算子に変換します。</span><span class="sxs-lookup"><span data-stu-id="e0cec-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="e0cec-106">入力</span><span class="sxs-lookup"><span data-stu-id="e0cec-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="e0cec-107">idx: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e0cec-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e0cec-108">`0..3`P# li 演算子に変換する範囲の整数。</span><span class="sxs-lookup"><span data-stu-id="e0cec-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="e0cec-109">出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="e0cec-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="e0cec-110">`Pauli`によって指定された演算子 `[PauliI, PauliX, PauliY, PauliZ][idx]` 。</span><span class="sxs-lookup"><span data-stu-id="e0cec-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>