---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 904c606393131d51eaa44d464ad52bec509eaf72
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204540"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="5db8a-102">WeightOnePaulis 関数</span><span class="sxs-lookup"><span data-stu-id="5db8a-102">WeightOnePaulis function</span></span>

<span data-ttu-id="5db8a-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5db8a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5db8a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5db8a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5db8a-105">指定された数の qubits に対するすべての重み-1 の Pan Li 演算子の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="5db8a-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="5db8a-106">入力</span><span class="sxs-lookup"><span data-stu-id="5db8a-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="5db8a-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5db8a-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5db8a-108">返された P# li 演算子が定義されている qubits の数。</span><span class="sxs-lookup"><span data-stu-id="5db8a-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="5db8a-109">出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="5db8a-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="5db8a-110">マルチビット演算子の配列。それぞれが長さの配列として表され `nQubits` ます。</span><span class="sxs-lookup"><span data-stu-id="5db8a-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>