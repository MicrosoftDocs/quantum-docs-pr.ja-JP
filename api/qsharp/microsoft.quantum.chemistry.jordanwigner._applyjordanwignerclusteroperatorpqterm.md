---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQTerm
title: _ApplyJordanWignerClusterOperatorPQTerm 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQTerm
qsharp.summary: Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: 67ec6fcfec097a14b1e31f94ac82ecf15109ecf6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851740"
---
# <a name="_applyjordanwignerclusteroperatorpqterm-operation"></a><span data-ttu-id="796f6-102">_ApplyJordanWignerClusterOperatorPQTerm 操作</span><span class="sxs-lookup"><span data-stu-id="796f6-102">_ApplyJordanWignerClusterOperatorPQTerm operation</span></span>

<span data-ttu-id="796f6-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="796f6-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="796f6-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="796f6-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="796f6-105">によって記述されるクラスターオペレーターの PQ 用語によって時間の進化を適用 `GeneratorIndex` します。</span><span class="sxs-lookup"><span data-stu-id="796f6-105">Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="796f6-106">入力</span><span class="sxs-lookup"><span data-stu-id="796f6-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="796f6-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="796f6-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="796f6-108">`GeneratorIndex` クラスターオペレーターの PQ 用語を表します。</span><span class="sxs-lookup"><span data-stu-id="796f6-108">`GeneratorIndex` representing a cluster operator PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="796f6-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="796f6-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="796f6-110">時間の進化の期間。</span><span class="sxs-lookup"><span data-stu-id="796f6-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="796f6-111">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="796f6-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="796f6-112">Hamiltonian の qubits。</span><span class="sxs-lookup"><span data-stu-id="796f6-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="796f6-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="796f6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

