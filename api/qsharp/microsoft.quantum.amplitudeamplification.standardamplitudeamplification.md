---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: StandardAmplitudeAmplification 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 984bfee89b6d79750228b8ca6aaf404f58aecd41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843924"
---
# <a name="standardamplitudeamplification-function"></a><span data-ttu-id="84bac-102">StandardAmplitudeAmplification 関数</span><span class="sxs-lookup"><span data-stu-id="84bac-102">StandardAmplitudeAmplification function</span></span>

<span data-ttu-id="84bac-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="84bac-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="84bac-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84bac-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84bac-105">標準の振幅増幅アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="84bac-105">Standard Amplitude Amplification algorithm</span></span>

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="84bac-106">入力</span><span class="sxs-lookup"><span data-stu-id="84bac-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="84bac-107">nIterations: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="84bac-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="84bac-108">振幅増幅数 $n の反復回数</span><span class="sxs-lookup"><span data-stu-id="84bac-108">Number of iterations $n$ of amplitude amplification</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="84bac-109">stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="84bac-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="84bac-110">開始状態を準備する oracle $A $ のユニタリ</span><span class="sxs-lookup"><span data-stu-id="84bac-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="84bac-111">idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="84bac-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="84bac-112">フラグ qubit へのインデックス</span><span class="sxs-lookup"><span data-stu-id="84bac-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="84bac-113">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="84bac-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="84bac-114">標準の振幅増幅クォンタムアルゴリズムを実装する操作</span><span class="sxs-lookup"><span data-stu-id="84bac-114">An operation that implements the standard amplitude amplification quantum algorithm</span></span>

## <a name="remarks"></a><span data-ttu-id="84bac-115">解説</span><span class="sxs-lookup"><span data-stu-id="84bac-115">Remarks</span></span>

<span data-ttu-id="84bac-116">これは、 `AmpAmpPhasesStandard` \Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} s + \sqrt{1-| \ ラムダ | ^ 2} \ket fcドットを想定して計算された、標準の振幅増幅アルゴリズムです。 \_ {0} \_ \end{align} この操作により、\begin{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \ sin ((2n + 1) \ sin ^ {-1} (\ ラムダ)) \ket {1} \_ f\ket {\ text {target}} \_ s + \cdots\ket f \end{align} の状態がほとんどの {0} \_ 場合に準備され、 `flagQubit` `auxiliaryRegister` 状態が $ \ket {0} \_ f\ket a $ に初期化され {0} \_ ます。</span><span class="sxs-lookup"><span data-stu-id="84bac-116">This is the standard amplitude amplification algorithm obtained by a choice of reflection phases computed by `AmpAmpPhasesStandard` Assuming that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} this operation prepares the state \begin{align} \operatorname{AmpAmpByOracle}\ket{0}\_{f}\ket{0}\_s= \sin((2n+1)\sin^{-1}(\lambda))\ket{1}\_f\ket{\text{target}}\_s + \cdots\ket{0}\_f \end{align} In most cases, `flagQubit` and `auxiliaryRegister` is initialized in the state $\ket{0}\_f\ket{0}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="84bac-117">References</span><span class="sxs-lookup"><span data-stu-id="84bac-117">References</span></span>

- [<span data-ttu-id="84bac-118">*Hoyer、m.、M、Mosca、A. Tapp。*</span><span class="sxs-lookup"><span data-stu-id="84bac-118"> *G. Brassard, P. Hoyer, M. Mosca, A. Tapp* </span></span>](https://arxiv.org/abs/quant-ph/0005055)