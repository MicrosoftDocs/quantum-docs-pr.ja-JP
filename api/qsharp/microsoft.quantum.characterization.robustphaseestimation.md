---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 3e6774e2fe348668840cdc08fe3a070ec3d82a6d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216083"
---
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="a478f-102">RobustPhaseEstimation 操作</span><span class="sxs-lookup"><span data-stu-id="a478f-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="a478f-103">名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="a478f-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="a478f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a478f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a478f-105">指定された oracle および eigenstate に対して、反復的ではない堅牢なクォンタムフェーズの推定アルゴリズムを実行 `U` し、ハイゼンベルグ limit での差異のスケーリングにより、フェーズの1つの実際の値の見積もりを提供します。</span><span class="sxs-lookup"><span data-stu-id="a478f-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="a478f-106">入力</span><span class="sxs-lookup"><span data-stu-id="a478f-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="a478f-107">bitsPrecision: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a478f-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a478f-108">これにより、$-シグマ/le 10.7 \ pi/\ text{# of queries} $ のような多数のクエリを使用して、標準偏差 $/シグマ/le 2 \ pi/2 ^ \text{bitsPrecision} $ の推定値が $/phi $ になります。</span><span class="sxs-lookup"><span data-stu-id="a478f-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="a478f-109">oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="a478f-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="a478f-110">指定された整数に $U ^ m $ を実装する操作では $m $ が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a478f-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="a478f-111">targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a478f-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a478f-112">$ Act を $U するクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="a478f-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="a478f-113">Eigenstate $ \ket{\phi} $ of $U $ が格納されている場合は $U、$ \phi\in (-\ pi,-pi) $ の \ket{\phi} = e ^ {i} \ket{\phi} $ が不明なフェーズになります。</span><span class="sxs-lookup"><span data-stu-id="a478f-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="a478f-114">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a478f-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="a478f-115">解説</span><span class="sxs-lookup"><span data-stu-id="a478f-115">Remarks</span></span>

<span data-ttu-id="a478f-116">クエリ数が多い場合、$/phi $ を満たす $/phi $ に対する標準偏差の下限を Cramer-Rao します (クエリの数は $/シグマ)。この値を超えると、クエリは {# of queries} $ となります。</span><span class="sxs-lookup"><span data-stu-id="a478f-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="a478f-117">リファレンス</span><span class="sxs-lookup"><span data-stu-id="a478f-117">References</span></span>

- <span data-ttu-id="a478f-118">堅牢なフェーズ推定 Shelby Kimmel、Guang Hao Low、Theodore J 氏によるユニバーサル Single-Qubit Gate-Set の堅牢な調整 https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="a478f-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>