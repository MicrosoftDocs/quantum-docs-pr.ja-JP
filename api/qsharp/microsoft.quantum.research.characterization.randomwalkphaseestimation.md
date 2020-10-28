---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: RandomWalkPhaseEstimation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: 5e0c0871b916ff51b85dec8703111788b5204bc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710880"
---
# <a name="randomwalkphaseestimation-operation"></a><span data-ttu-id="4f15e-102">RandomWalkPhaseEstimation 操作</span><span class="sxs-lookup"><span data-stu-id="4f15e-102">RandomWalkPhaseEstimation operation</span></span>

<span data-ttu-id="4f15e-103">名前空間: [Microsoft. Quantum. 特性](xref:Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="4f15e-103">Namespace: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span></span>

<span data-ttu-id="4f15e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4f15e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4f15e-105">指定された oracle および eigenstate からの古典的な測定結果に対するベイジアン推定を概算するランダムウォークを使用して反復フェーズ推定を実行します。</span><span class="sxs-lookup"><span data-stu-id="4f15e-105">Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.</span></span>

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="4f15e-106">入力</span><span class="sxs-lookup"><span data-stu-id="4f15e-106">Input</span></span>

### <a name="initialmean--double"></a><span data-ttu-id="4f15e-107">initialMean: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4f15e-107">initialMean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4f15e-108">最初の標準正規分布の平均値 $-phi $。</span><span class="sxs-lookup"><span data-stu-id="4f15e-108">Mean of the initial normal prior distribution over $\phi$.</span></span>


### <a name="initialstddev--double"></a><span data-ttu-id="4f15e-109">initialStdDev: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4f15e-109">initialStdDev : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4f15e-110">初期正規分布の標準偏差 ($/phi $ 経由)。</span><span class="sxs-lookup"><span data-stu-id="4f15e-110">Standard deviation of the initial normal prior distribution over $\phi$.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="4f15e-111">nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f15e-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4f15e-112">最終的な事後見積もらに許容される測定値の数。</span><span class="sxs-lookup"><span data-stu-id="4f15e-112">Number of measurements to be accepted into the final posterior estimate.</span></span>


### <a name="maxmeasurements--int"></a><span data-ttu-id="4f15e-113">maxMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f15e-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4f15e-114">操作が失敗したと見なされるまでに取得できる測定の合計数。</span><span class="sxs-lookup"><span data-stu-id="4f15e-114">Total number of measurements than can be taken before the operation is considered to have failed.</span></span>


### <a name="unwind--int"></a><span data-ttu-id="4f15e-115">アンワインド: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f15e-115">unwind : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4f15e-116">整合性チェックが失敗した場合に破棄する結果の数。</span><span class="sxs-lookup"><span data-stu-id="4f15e-116">Number of results to forget when consistency checks fail.</span></span>


### <a name="oracle--continuousoracle"></a><span data-ttu-id="4f15e-117">oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="4f15e-117">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="4f15e-118">$U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $ (不明なフェーズ $ \ phi \、\mathbb{R} ^ + $) を含む、型の $U $ を表す演算。</span><span class="sxs-lookup"><span data-stu-id="4f15e-118">An operation representing a unitary $U$ such that $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ for eigenstates $\ket{\phi}$ with unknown phase $\phi \in \mathbb{R}^+$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="4f15e-119">targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4f15e-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4f15e-120">$ Act $U れるレジスタ。</span><span class="sxs-lookup"><span data-stu-id="4f15e-120">A register that $U$ acts on.</span></span>



## <a name="output--double"></a><span data-ttu-id="4f15e-121">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4f15e-121">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4f15e-122">最終的な推定 $ \hat{\phi} \mathrel{: =} \ [-phi] $ が期待される場合は、事後によって受け入れられるすべてのデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="4f15e-122">The final estimate $\hat{\phi} \mathrel{:=} \expect[\phi]$ , where the expectation is over the posterior given all accepted data.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f15e-123">解説</span><span class="sxs-lookup"><span data-stu-id="4f15e-123">Remarks</span></span>

### <a name="iterative-phase-estimation-and-eigenstates"></a><span data-ttu-id="4f15e-124">反復フェーズの推定と Eigenstates</span><span class="sxs-lookup"><span data-stu-id="4f15e-124">Iterative Phase Estimation and Eigenstates</span></span>

<span data-ttu-id="4f15e-125">一般に、入力レジスタは `eigenstate` $U $ の eigenstate $ \ket{\phi} $ である必要はありませんが、eigenstate の法則にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f15e-125">In general, the input register `eigenstate` need not be an eigenstate $\ket{\phi}$ of $U$, but can be a superposition over eigenstates.</span></span> <span data-ttu-id="4f15e-126">入力状態が指定されていることを想定しています。 \begin{align} \ket{\psi} & = \ sum \_ {j}-alpha \_ j \ket{\phi \_ j}, \end{align}、$- \{ alpha j \_ \} $ は複雑な係数で、$ \ sum \_ j | \ alpha \_ j | ^ 2 = $1、where $U \ket{\phi \_ j} = \ phi \_ j\ket {\ phi \_ j} $。</span><span class="sxs-lookup"><span data-stu-id="4f15e-126">Suppose that the input state is given by \begin{align} \ket{\psi} & = \sum\_{j} \alpha\_j \ket{\phi\_j}, \end{align} where $\{\alpha\_j\}$ are complex coefficients such that $\sum\_j |\alpha\_j|^2 = 1$ and where $U\ket{\phi\_j} = \phi\_j\ket{\phi\_j}$.</span></span>

<span data-ttu-id="4f15e-127">次に、 [開発ガイド](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates)で説明されているように、反復フェーズの推定を実行すると、最終的に1つの eigenstate に収束します。</span><span class="sxs-lookup"><span data-stu-id="4f15e-127">Then, performing iterative phase estimation will eventually converge to a single eigenstate, as described in the [development guide](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span></span>

### <a name="experiment-design"></a><span data-ttu-id="4f15e-128">実験の設計</span><span class="sxs-lookup"><span data-stu-id="4f15e-128">Experiment Design</span></span>

<span data-ttu-id="4f15e-129">に渡された $t $ と反転角度 $ \ シータ $ の測定時間は、 `oracle` *パーティクル推測のヒューリスティック* 、\begin{align} (-phi)、および \variance{\phi}}. に従って選択されます。 {1}</span><span class="sxs-lookup"><span data-stu-id="4f15e-129">The measurement times $t$ and inversion angles $\theta$ passed to `oracle` are chosen according to the *particle guess heuristic* , \begin{align} \theta \sim \Pr(\phi),\quad t \approx \frac{1}{\variance{\phi}}.</span></span>
<span data-ttu-id="4f15e-130">\end{align} このヒューリスティックは、予期される事後分散を、標準の前提条件下で反復フェーズ推定で削減するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="4f15e-130">\end{align} This heuristic is optimal for reducing the expected posterior variance in iterative phase estimation under the assumption of a normal prior.</span></span>

### <a name="optimality"></a><span data-ttu-id="4f15e-131">たいてい</span><span class="sxs-lookup"><span data-stu-id="4f15e-131">Optimality</span></span>

<span data-ttu-id="4f15e-132">この操作では、2次損失 $L (\ phi, \hat{\phi}) \mathrel{: =} (\hat{\phi}) ^ 2 $ を使用して評価された、フェーズ $/phi $ の最適な推定に近似されます。</span><span class="sxs-lookup"><span data-stu-id="4f15e-132">This operation approximates the optimal estimator for the phase $\phi$, as evaluated using the quadratic loss $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span></span>

<span data-ttu-id="4f15e-133">反復フェーズ推定の統計の詳細については、「 [ベイジアンフェーズの推定](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f15e-133">See [Bayesian Phase Estimation](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) for more details on the statistics of iterative phase estimation.</span></span>

## <a name="references"></a><span data-ttu-id="4f15e-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f15e-134">References</span></span>

- <span data-ttu-id="4f15e-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6)、 [arxiv: 1110.3067](https://arxiv.org/abs/1110.3067)。</span><span class="sxs-lookup"><span data-stu-id="4f15e-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6), [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span></span>
- <span data-ttu-id="4f15e-136">Wiebe *2013* [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501)、 [arxiv: 1309.0876](https://arxiv.org/abs/1309.0876)</span><span class="sxs-lookup"><span data-stu-id="4f15e-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span></span>
- <span data-ttu-id="4f15e-137">Wiebe と Granade 2018 *(準備中)* 。</span><span class="sxs-lookup"><span data-stu-id="4f15e-137">Wiebe and Granade 2018 *(in preparation)* .</span></span>