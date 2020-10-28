---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQTerm
title: _ApplyJordanWignerClusterOperatorPQTerm 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQTerm
qsharp.summary: Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: d72ddea439c45936caefa74add4a0444afe4318e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714814"
---
# <a name="_applyjordanwignerclusteroperatorpqterm-operation"></a><span data-ttu-id="eec79-102">_ApplyJordanWignerClusterOperatorPQTerm 操作</span><span class="sxs-lookup"><span data-stu-id="eec79-102">_ApplyJordanWignerClusterOperatorPQTerm operation</span></span>

<span data-ttu-id="eec79-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="eec79-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="eec79-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eec79-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eec79-105">によって記述されるクラスターオペレーターの PQ 用語によって時間の進化を適用 `GeneratorIndex` します。</span><span class="sxs-lookup"><span data-stu-id="eec79-105">Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="eec79-106">入力</span><span class="sxs-lookup"><span data-stu-id="eec79-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="eec79-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="eec79-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="eec79-108">`GeneratorIndex` クラスターオペレーターの PQ 用語を表します。</span><span class="sxs-lookup"><span data-stu-id="eec79-108">`GeneratorIndex` representing a cluster operator PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="eec79-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eec79-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eec79-110">時間の進化の期間。</span><span class="sxs-lookup"><span data-stu-id="eec79-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="eec79-111">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="eec79-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="eec79-112">Hamiltonian の qubits。</span><span class="sxs-lookup"><span data-stu-id="eec79-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eec79-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eec79-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

