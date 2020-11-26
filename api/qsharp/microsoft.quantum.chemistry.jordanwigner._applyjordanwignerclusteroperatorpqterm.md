---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQTerm
title: _ApplyJordanWignerClusterOperatorPQTerm 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQTerm
qsharp.summary: Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: d39f74721a518328bb9f3b1513e15aebe58b3612
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215947"
---
# <a name="_applyjordanwignerclusteroperatorpqterm-operation"></a><span data-ttu-id="3ae2a-102">_ApplyJordanWignerClusterOperatorPQTerm 操作</span><span class="sxs-lookup"><span data-stu-id="3ae2a-102">_ApplyJordanWignerClusterOperatorPQTerm operation</span></span>

<span data-ttu-id="3ae2a-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="3ae2a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="3ae2a-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3ae2a-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="3ae2a-105">によって記述されるクラスターオペレーターの PQ 用語によって時間の進化を適用 `GeneratorIndex` します。</span><span class="sxs-lookup"><span data-stu-id="3ae2a-105">Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3ae2a-106">入力</span><span class="sxs-lookup"><span data-stu-id="3ae2a-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="3ae2a-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3ae2a-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3ae2a-108">`GeneratorIndex` クラスターオペレーターの PQ 用語を表します。</span><span class="sxs-lookup"><span data-stu-id="3ae2a-108">`GeneratorIndex` representing a cluster operator PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="3ae2a-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3ae2a-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3ae2a-110">時間の進化の期間。</span><span class="sxs-lookup"><span data-stu-id="3ae2a-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="3ae2a-111">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3ae2a-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3ae2a-112">Hamiltonian の qubits。</span><span class="sxs-lookup"><span data-stu-id="3ae2a-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ae2a-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ae2a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

