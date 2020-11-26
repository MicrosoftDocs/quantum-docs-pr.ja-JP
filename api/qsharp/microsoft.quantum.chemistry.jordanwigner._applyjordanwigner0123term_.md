---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWigner0123Term_
title: _ApplyJordanWigner0123Term_ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWigner0123Term_
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: bdc0b693a653761a89fa975325150de80440d18c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215981"
---
# <a name="_applyjordanwigner0123term_-operation"></a><span data-ttu-id="3d4d4-102">_ApplyJordanWigner0123Term_ 操作</span><span class="sxs-lookup"><span data-stu-id="3d4d4-102">_ApplyJordanWigner0123Term_ operation</span></span>

<span data-ttu-id="3d4d4-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="3d4d4-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="3d4d4-105">によって記述された PQRS 用語によって時間の進化を適用 `GeneratorIndex` します。</span><span class="sxs-lookup"><span data-stu-id="3d4d4-105">Applies time-evolution by a PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWigner0123Term_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3d4d4-106">入力</span><span class="sxs-lookup"><span data-stu-id="3d4d4-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="3d4d4-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3d4d4-108">`GeneratorIndex` PQRS 用語を表す。</span><span class="sxs-lookup"><span data-stu-id="3d4d4-108">`GeneratorIndex` representing a PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="3d4d4-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3d4d4-110">時間の進化の期間。</span><span class="sxs-lookup"><span data-stu-id="3d4d4-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="3d4d4-111">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3d4d4-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3d4d4-112">Hamiltonian の qubits。</span><span class="sxs-lookup"><span data-stu-id="3d4d4-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3d4d4-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3d4d4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

