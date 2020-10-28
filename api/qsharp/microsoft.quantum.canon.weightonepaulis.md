---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 89802c1bc6f3da8edef27b698eb61098e47dfc85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715197"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="e4e6f-102">WeightOnePaulis 関数</span><span class="sxs-lookup"><span data-stu-id="e4e6f-102">WeightOnePaulis function</span></span>

<span data-ttu-id="e4e6f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e4e6f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e4e6f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4e6f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4e6f-105">指定された数の qubits に対するすべての重み-1 の Pan Li 演算子の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="e4e6f-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="e4e6f-106">入力</span><span class="sxs-lookup"><span data-stu-id="e4e6f-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="e4e6f-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4e6f-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4e6f-108">返された P# li 演算子が定義されている qubits の数。</span><span class="sxs-lookup"><span data-stu-id="e4e6f-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="e4e6f-109">出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="e4e6f-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="e4e6f-110">マルチビット演算子の配列。それぞれが長さの配列として表され `nQubits` ます。</span><span class="sxs-lookup"><span data-stu-id="e4e6f-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>