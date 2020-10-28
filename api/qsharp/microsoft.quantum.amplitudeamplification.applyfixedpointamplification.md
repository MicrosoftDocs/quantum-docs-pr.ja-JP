---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: f506be7b2e3f65cf89694e30d79c04ec30d25035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721907"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="3be64-102">ApplyFixedPointAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="3be64-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="3be64-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="3be64-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="3be64-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3be64-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3be64-105">Fixed-Point 振幅増幅アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="3be64-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3be64-106">入力</span><span class="sxs-lookup"><span data-stu-id="3be64-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="3be64-107">statePrepOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="3be64-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="3be64-108">開始状態を準備する oracle のユニタリ。</span><span class="sxs-lookup"><span data-stu-id="3be64-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="3be64-109">startQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3be64-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3be64-110">Qubit レジスタ</span><span class="sxs-lookup"><span data-stu-id="3be64-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="3be64-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3be64-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3be64-112">解説</span><span class="sxs-lookup"><span data-stu-id="3be64-112">Remarks</span></span>

<span data-ttu-id="3be64-113">StartQubits は、$ \ket{0 \ cドット 0} $ 状態である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be64-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="3be64-114">この操作では、最大数のクエリに到達するか、ターゲットの状態が検出されるまで、$2 $ の累乗による多数のクエリを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="3be64-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>