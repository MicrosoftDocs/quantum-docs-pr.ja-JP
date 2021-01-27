---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: c171021272076cc3960307523e25c4493bb49c5a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845869"
---
# <a name="applyobliviousamplitudeamplification-operation"></a><span data-ttu-id="d3585-102">ApplyObliviousAmplitudeAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="d3585-102">ApplyObliviousAmplitudeAmplification operation</span></span>

<span data-ttu-id="d3585-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d3585-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d3585-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3585-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3585-105">部分的な反射を指定することによって、振幅増幅を無関係します。</span><span class="sxs-lookup"><span data-stu-id="d3585-105">Oblivious amplitude amplification by specifying partial reflections.</span></span>

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d3585-106">入力</span><span class="sxs-lookup"><span data-stu-id="d3585-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="d3585-107">フェーズ: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="d3585-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="d3585-108">部分的な反射のフェーズ</span><span class="sxs-lookup"><span data-stu-id="d3585-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="d3585-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="d3585-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="d3585-110">補助レジスタの開始状態に関するリフレクション演算子</span><span class="sxs-lookup"><span data-stu-id="d3585-110">Reflection operator about start state of auxiliary register</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="d3585-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="d3585-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="d3585-112">補助レジスタのターゲット状態に関するリフレクション演算子</span><span class="sxs-lookup"><span data-stu-id="d3585-112">Reflection operator about target state of auxiliary register</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="d3585-113">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="d3585-113">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="d3585-114">`ObliviousOracle`補助レジスタとシステムレジスタに共同で動作する型の、oracle $O $ のユニタリ。</span><span class="sxs-lookup"><span data-stu-id="d3585-114">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system registers.</span></span>


### <a name="auxiliaryregister--qubit"></a><span data-ttu-id="d3585-115">auxiliaryRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d3585-115">auxiliaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d3585-116">補助レジスタ</span><span class="sxs-lookup"><span data-stu-id="d3585-116">Auxiliary register</span></span>


### <a name="systemregister--qubit"></a><span data-ttu-id="d3585-117">systemRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d3585-117">systemRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d3585-118">システムレジスタ</span><span class="sxs-lookup"><span data-stu-id="d3585-118">System register</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3585-119">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3585-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d3585-120">解説</span><span class="sxs-lookup"><span data-stu-id="d3585-120">Remarks</span></span>

<span data-ttu-id="d3585-121">特定の補助開始状態が指定されている場合 $ \ket{\text{start}} \_ a $, 特定の補助ターゲットの状態 $ \ket{\text{target}} \_ a $、および任意のシステム状態 $ \ket{\psi} \_ s $ では、一部の $U $ について、\begin{align} O\ket {\ text {start}} \_ a\ket {\ psi} \_ s = \lambda\ket{\text{target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \_ a \ket{\text{target} とします。</span><span class="sxs-lookup"><span data-stu-id="d3585-121">Given a particular auxiliary start state $\ket{\text{start}}\_a$, a particular auxiliary target state $\ket{\text{target}}\_a$, and any system state $\ket{\psi}\_s$, suppose that \begin{align} O\ket{\text{start}}\_a\ket{\psi}\_s= \lambda\ket{\text{target}}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{\text{target}^\perp}\_a\cdots \end{align} for some unitary $U$.</span></span>
<span data-ttu-id="d3585-122">のアプリケーションとその adjoint によってインターリーブされる補助レジスタの開始状態とターゲット状態に関する一連の反射によって `signalOracle` 、U を適用する成功確率が変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d3585-122">By a sequence of reflections about the start and target states on the auxiliary register interleaved by applications of `signalOracle` and its adjoint, the success probability of applying U may be altered.</span></span>

<span data-ttu-id="d3585-123">ほとんどの場合、 `auxiliaryRegister` は、$ \ket{\text{start}} a $ という状態で初期化され \_ ます。</span><span class="sxs-lookup"><span data-stu-id="d3585-123">In most cases, `auxiliaryRegister` is initialized in the state $\ket{\text{start}}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="d3585-124">References</span><span class="sxs-lookup"><span data-stu-id="d3585-124">References</span></span>

<span data-ttu-id="d3585-125">解決方法については、</span><span class="sxs-lookup"><span data-stu-id="d3585-125">See</span></span>

- <span data-ttu-id="d3585-126">[ *D.W. Berry、A.M. Childs、Cleve、Kothari、R.D. Somma、*](https://arxiv.org/abs/1312.1414) standard バージョン。</span><span class="sxs-lookup"><span data-stu-id="d3585-126">[ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma* ](https://arxiv.org/abs/1312.1414) for the standard version.</span></span>
  <span data-ttu-id="d3585-127">解決方法については、</span><span class="sxs-lookup"><span data-stu-id="d3585-127">See</span></span>
- <span data-ttu-id="d3585-128">[ *G.H. Low、I.L. 語*](https://arxiv.org/abs/1610.06546)を部分的な反射に使用します。</span><span class="sxs-lookup"><span data-stu-id="d3585-128">[ *G.H. Low, I.L. Chuang* ](https://arxiv.org/abs/1610.06546) for a generalization to partial reflections.</span></span>