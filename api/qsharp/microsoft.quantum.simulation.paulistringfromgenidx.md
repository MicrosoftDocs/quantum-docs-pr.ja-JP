---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: P# listringfromgenidx 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 33da4bc3d7e58b87aef75b453b6af09a51214923
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710544"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="0e539-102">P# listringfromgenidx 関数</span><span class="sxs-lookup"><span data-stu-id="0e539-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="0e539-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0e539-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0e539-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e539-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e539-105">によって記述される psystem.string li 文字列とその qubit インデックスを抽出し `GeneratorIndex` ます。</span><span class="sxs-lookup"><span data-stu-id="0e539-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="0e539-106">入力</span><span class="sxs-lookup"><span data-stu-id="0e539-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="0e539-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="0e539-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="0e539-108">`GeneratorIndex` Pをエンコードする型。</span><span class="sxs-lookup"><span data-stu-id="0e539-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="0e539-109">出力: ([P# li](xref:microsoft.quantum.lang-ref.pauli)[]、[Int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="0e539-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="0e539-110">によって記述された用語の P# li 文字列と、その処理を `GeneratorIndex` 行う qubits へのインデックス。</span><span class="sxs-lookup"><span data-stu-id="0e539-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>