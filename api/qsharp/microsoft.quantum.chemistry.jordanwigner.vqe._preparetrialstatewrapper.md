---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: _prepareTrialStateWrapper 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: bfd7b9ce8e8b2c8f322d676c640f8c2488655516
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713764"
---
# <a name="_preparetrialstatewrapper-operation"></a><span data-ttu-id="7594e-102">_prepareTrialStateWrapper 操作</span><span class="sxs-lookup"><span data-stu-id="7594e-102">_prepareTrialStateWrapper operation</span></span>

<span data-ttu-id="7594e-103">名前空間: [JordanWigner です。 VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="7594e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="7594e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7594e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7594e-105">Adjoint を定義することで、EstimateFrequencyA との互換性を確保するための PrepareTrialState のプライベートラッパー。</span><span class="sxs-lookup"><span data-stu-id="7594e-105">Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint.</span></span>
<span data-ttu-id="7594e-106">EstimateFrequencyA には、QuantumSimulator を対象とする組み込みのエミュレーション機能があり、実行速度が上がります。</span><span class="sxs-lookup"><span data-stu-id="7594e-106">EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.</span></span>

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7594e-107">入力</span><span class="sxs-lookup"><span data-stu-id="7594e-107">Input</span></span>

### <a name="inputstate--intjordanwignerinputstate"></a><span data-ttu-id="7594e-108">inputState: ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span><span class="sxs-lookup"><span data-stu-id="7594e-108">inputState : ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span></span>

<span data-ttu-id="7594e-109">PrepareTrialState を実行するために必要な Jordan-Wigner 入力です。</span><span class="sxs-lookup"><span data-stu-id="7594e-109">The Jordan-Wigner input required for PrepareTrialState to run.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="7594e-110">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7594e-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7594e-111">Qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="7594e-111">A qubit register.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7594e-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7594e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

