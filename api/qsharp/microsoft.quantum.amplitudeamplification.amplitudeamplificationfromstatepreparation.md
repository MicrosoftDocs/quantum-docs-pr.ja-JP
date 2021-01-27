---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: e64ad5ad4e975483f20f92c0b070dd6788ef296b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847452"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="95c85-102">AmplitudeAmplificationFromStatePreparation 関数</span><span class="sxs-lookup"><span data-stu-id="95c85-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="95c85-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="95c85-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="95c85-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95c85-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95c85-105">部分的な反射のための oracles による振幅増幅。</span><span class="sxs-lookup"><span data-stu-id="95c85-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="95c85-106">入力</span><span class="sxs-lookup"><span data-stu-id="95c85-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="95c85-107">フェーズ: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="95c85-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="95c85-108">部分的な反射のフェーズ</span><span class="sxs-lookup"><span data-stu-id="95c85-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="95c85-109">stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="95c85-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="95c85-110">開始状態を準備する oracle $A $ のユニタリ</span><span class="sxs-lookup"><span data-stu-id="95c85-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="95c85-111">idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95c85-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="95c85-112">フラグ qubit へのインデックス</span><span class="sxs-lookup"><span data-stu-id="95c85-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="95c85-113">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="95c85-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="95c85-114">部分的な反射によって実装される、oracles による振幅増幅を実装する操作。</span><span class="sxs-lookup"><span data-stu-id="95c85-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="95c85-115">解説</span><span class="sxs-lookup"><span data-stu-id="95c85-115">Remarks</span></span>

<span data-ttu-id="95c85-116">これにより、の開始と送信先の状態の形式に対してより厳密な条件が課さ `AmpAmpByReflectionPhases` れます。</span><span class="sxs-lookup"><span data-stu-id="95c85-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="95c85-117">ターゲットの状態が $ \ket f $ によってマークされていることを前提としてい {1} \_ ます。</span><span class="sxs-lookup"><span data-stu-id="95c85-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="95c85-118">\Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} \_ s + \sqrt{1-| \ ラムダ | ^ 2} \ket \end{align} \ket | \ lambda | ^ 2} \ket {0} \_ (ほとんどの場合、) は、 `flagQubit` `auxiliaryRegister` $ {0} \_ {f} s $ の状態で初期化さ {0} \_ れることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="95c85-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>