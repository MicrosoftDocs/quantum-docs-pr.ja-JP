---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZTerm
title: _JWOptimizedZTerm 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZTerm
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: 0b54bd7916ff8294501716365c11211b4654f5ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722789"
---
# <a name="_jwoptimizedzterm-operation"></a><span data-ttu-id="38382-102">_JWOptimizedZTerm 操作</span><span class="sxs-lookup"><span data-stu-id="38382-102">_JWOptimizedZTerm operation</span></span>

<span data-ttu-id="38382-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="38382-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="38382-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="38382-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="38382-105">によって記述された Z 語による時間の推移を適用 `GeneratorIndex` します。</span><span class="sxs-lookup"><span data-stu-id="38382-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="38382-106">入力</span><span class="sxs-lookup"><span data-stu-id="38382-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="38382-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="38382-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="38382-108">`GeneratorIndex` Z 語を表す。</span><span class="sxs-lookup"><span data-stu-id="38382-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="38382-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="38382-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="38382-110">時間の進化の期間。</span><span class="sxs-lookup"><span data-stu-id="38382-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="38382-111">parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="38382-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="38382-112">タイム進化の符号を決定する qubit。</span><span class="sxs-lookup"><span data-stu-id="38382-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="38382-113">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="38382-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="38382-114">Hamiltonian の qubits。</span><span class="sxs-lookup"><span data-stu-id="38382-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="38382-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="38382-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

