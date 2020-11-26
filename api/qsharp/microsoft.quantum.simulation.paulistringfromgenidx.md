---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: P# listringfromgenidx 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: a937dc648c5de5a5f6de7da996448af497b92185
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230312"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="abf1a-102">P# listringfromgenidx 関数</span><span class="sxs-lookup"><span data-stu-id="abf1a-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="abf1a-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="abf1a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="abf1a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="abf1a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="abf1a-105">によって記述される psystem.string li 文字列とその qubit インデックスを抽出し `GeneratorIndex` ます。</span><span class="sxs-lookup"><span data-stu-id="abf1a-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="abf1a-106">入力</span><span class="sxs-lookup"><span data-stu-id="abf1a-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="abf1a-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="abf1a-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="abf1a-108">`GeneratorIndex` Pをエンコードする型。</span><span class="sxs-lookup"><span data-stu-id="abf1a-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="abf1a-109">出力: ([P# li](xref:microsoft.quantum.lang-ref.pauli)[]、[Int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="abf1a-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="abf1a-110">によって記述された用語の P# li 文字列と、その処理を `GeneratorIndex` 行う qubits へのインデックス。</span><span class="sxs-lookup"><span data-stu-id="abf1a-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>