---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: Inttop/Li 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724847"
---
# <a name="inttopauli-function"></a><span data-ttu-id="460bd-102">Inttop/Li 関数</span><span class="sxs-lookup"><span data-stu-id="460bd-102">IntToPauli function</span></span>

<span data-ttu-id="460bd-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="460bd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="460bd-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="460bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="460bd-105">整数をシングル qubit の P# li 演算子に変換します。</span><span class="sxs-lookup"><span data-stu-id="460bd-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="460bd-106">入力</span><span class="sxs-lookup"><span data-stu-id="460bd-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="460bd-107">idx: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="460bd-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="460bd-108">`0..3`P# li 演算子に変換する範囲の整数。</span><span class="sxs-lookup"><span data-stu-id="460bd-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="460bd-109">出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="460bd-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="460bd-110">`Pauli`によって指定された演算子 `[PauliI, PauliX, PauliY, PauliZ][idx]` 。</span><span class="sxs-lookup"><span data-stu-id="460bd-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>