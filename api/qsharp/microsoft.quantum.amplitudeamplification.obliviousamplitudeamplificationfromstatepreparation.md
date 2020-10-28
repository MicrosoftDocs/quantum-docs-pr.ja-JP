---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721832"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="311c0-102">ObliviousAmplitudeAmplificationFromStatePreparation 関数</span><span class="sxs-lookup"><span data-stu-id="311c0-102">ObliviousAmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="311c0-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="311c0-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="311c0-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="311c0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="311c0-105">部分的な反射のために oracles による振幅増幅を無関係します。</span><span class="sxs-lookup"><span data-stu-id="311c0-105">Oblivious amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="311c0-106">入力</span><span class="sxs-lookup"><span data-stu-id="311c0-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="311c0-107">フェーズ: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="311c0-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="311c0-108">部分的な反射のフェーズ</span><span class="sxs-lookup"><span data-stu-id="311c0-108">Phases of partial reflections</span></span>


### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="311c0-109">startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="311c0-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="311c0-110">補助開始状態を準備する oracle $A $ のユニタリ</span><span class="sxs-lookup"><span data-stu-id="311c0-110">Unitary oracle $A$ that prepares auxiliary start state</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="311c0-111">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="311c0-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="311c0-112">`ObliviousOracle`補助レジスタとシステムレジスタに共同で動作する型の、oracle $O $ のユニタリ</span><span class="sxs-lookup"><span data-stu-id="311c0-112">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system register</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="311c0-113">idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="311c0-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="311c0-114">シングル qubit フラグ登録のインデックス</span><span class="sxs-lookup"><span data-stu-id="311c0-114">Index to single-qubit flag register</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="311c0-115">出力: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit) の調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="311c0-115">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="311c0-116">部分的な反射に基づいて無関係の振幅増幅を実装する操作。</span><span class="sxs-lookup"><span data-stu-id="311c0-116">An operation that implements oblivious amplitude amplification based on partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="311c0-117">解説</span><span class="sxs-lookup"><span data-stu-id="311c0-117">Remarks</span></span>

<span data-ttu-id="311c0-118">これにより、のような補助開始状態とターゲット状態の形式に対して、より厳密な条件が課さ `AmpAmpObliviousByReflectionPhases` れます。</span><span class="sxs-lookup"><span data-stu-id="311c0-118">This imposes stricter conditions on form of the auxiliary start and target states than in `AmpAmpObliviousByReflectionPhases`.</span></span>
<span data-ttu-id="311c0-119">$A \ket {0} \_ f\ket {0} \_ A = \ket{\text{start}} \_ {fa} $ は、 \_ 計算ベース $ \ket f\ket $ から補助開始状態 $ \ket{\text{start}} {fa} $ を準備 {0} \_ {0} することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="311c0-119">It is assumed that $A\ket{0}\_f\ket{0}\_a= \ket{\text{start}}\_{fa}$ prepares the auxiliary start state $\ket{\text{start}}\_{fa}$ from the computational basis $\ket{0}\_f\ket{0}$.</span></span>
<span data-ttu-id="311c0-120">ターゲットの状態が $ \ket f $ によってマークされていることを前提としてい {1} \_ ます。</span><span class="sxs-lookup"><span data-stu-id="311c0-120">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="311c0-121">\Begin{align} O\ket {\ text {start}} \_ {fa} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {すべて}} \_ a\ket {\ text {target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \ lambda | ^ 2} \ket \end{align}; {0} \_ (一部のユニタリ $U $) を想定しています。</span><span class="sxs-lookup"><span data-stu-id="311c0-121">It is assumed that \begin{align} O\ket{\text{start}}\_{fa}\ket{\psi}\_s= \lambda\ket{1}\_f\ket{\text{anything}}\_a\ket{\text{target}}\_s U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} for some unitary $U$.</span></span>