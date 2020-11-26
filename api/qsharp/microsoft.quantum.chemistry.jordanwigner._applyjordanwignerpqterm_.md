---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQTerm_
title: _ApplyJordanWignerPQTerm_ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQTerm_
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: ef9ed8a9361548730d716cf0fea8ff08c82b6f59
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215913"
---
# <a name="_applyjordanwignerpqterm_-operation"></a><span data-ttu-id="b6471-102">_ApplyJordanWignerPQTerm_ 操作</span><span class="sxs-lookup"><span data-stu-id="b6471-102">_ApplyJordanWignerPQTerm_ operation</span></span>

<span data-ttu-id="b6471-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="b6471-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="b6471-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b6471-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="b6471-105">によって記述された PQ 用語によって時間の進化を適用 `GeneratorIndex` します。</span><span class="sxs-lookup"><span data-stu-id="b6471-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerPQTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, extraParityQubits : Qubit[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b6471-106">入力</span><span class="sxs-lookup"><span data-stu-id="b6471-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="b6471-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="b6471-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="b6471-108">`GeneratorIndex` PQ 用語を表します。</span><span class="sxs-lookup"><span data-stu-id="b6471-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="b6471-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6471-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6471-110">時間の進化の期間。</span><span class="sxs-lookup"><span data-stu-id="b6471-110">Duration of time-evolution.</span></span>


### <a name="extraparityqubits--qubit"></a><span data-ttu-id="b6471-111">extraParityQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b6471-111">extraParityQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b6471-112">タイム進化の符号を反転するオプションのパリティ qubits。</span><span class="sxs-lookup"><span data-stu-id="b6471-112">Optional parity qubits that flip the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="b6471-113">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b6471-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b6471-114">Hamiltonian の qubits。</span><span class="sxs-lookup"><span data-stu-id="b6471-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b6471-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6471-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

