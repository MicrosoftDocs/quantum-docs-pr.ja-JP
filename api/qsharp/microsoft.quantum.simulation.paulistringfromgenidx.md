---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: P# listringfromgenidx 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 048f91411099d24f3c0c5fd8ae3703779e7ab8a2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847906"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="960bf-102">P# listringfromgenidx 関数</span><span class="sxs-lookup"><span data-stu-id="960bf-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="960bf-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="960bf-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="960bf-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="960bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="960bf-105">によって記述される psystem.string li 文字列とその qubit インデックスを抽出し `GeneratorIndex` ます。</span><span class="sxs-lookup"><span data-stu-id="960bf-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="960bf-106">入力</span><span class="sxs-lookup"><span data-stu-id="960bf-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="960bf-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="960bf-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="960bf-108">`GeneratorIndex` Pをエンコードする型。</span><span class="sxs-lookup"><span data-stu-id="960bf-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="960bf-109">出力: ([P# li](xref:microsoft.quantum.lang-ref.pauli)[]、[Int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="960bf-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="960bf-110">によって記述された用語の P# li 文字列と、その処理を `GeneratorIndex` 行う qubits へのインデックス。</span><span class="sxs-lookup"><span data-stu-id="960bf-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>