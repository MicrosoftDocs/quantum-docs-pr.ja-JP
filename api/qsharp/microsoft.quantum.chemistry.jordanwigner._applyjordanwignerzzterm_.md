---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZZTerm_
title: _ApplyJordanWignerZZTerm_ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZZTerm_
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 9f03255d53f7ed7f3e79689ea53c8b95133f6cde
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714721"
---
# <a name="_applyjordanwignerzzterm_-operation"></a><span data-ttu-id="af01b-102">_ApplyJordanWignerZZTerm_ 操作</span><span class="sxs-lookup"><span data-stu-id="af01b-102">_ApplyJordanWignerZZTerm_ operation</span></span>

<span data-ttu-id="af01b-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="af01b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="af01b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="af01b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="af01b-105">によって記述された ZZ 用語によって時間の進化を適用 `GeneratorIndex` します。</span><span class="sxs-lookup"><span data-stu-id="af01b-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="af01b-106">入力</span><span class="sxs-lookup"><span data-stu-id="af01b-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="af01b-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="af01b-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="af01b-108">`GeneratorIndex` ZZ 用語を表します。</span><span class="sxs-lookup"><span data-stu-id="af01b-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="af01b-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="af01b-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="af01b-110">時間の進化の期間。</span><span class="sxs-lookup"><span data-stu-id="af01b-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="af01b-111">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="af01b-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="af01b-112">Hamiltonian の qubits。</span><span class="sxs-lookup"><span data-stu-id="af01b-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="af01b-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="af01b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

