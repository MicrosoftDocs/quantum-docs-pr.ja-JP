---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 30e1cf6e353b8a4491e13a9e2f588ec9cc103cb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191603"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="b52c7-102">AmplitudeAmplificationFromStatePreparation 関数</span><span class="sxs-lookup"><span data-stu-id="b52c7-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="b52c7-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="b52c7-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="b52c7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b52c7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b52c7-105">部分的な反射のための oracles による振幅増幅。</span><span class="sxs-lookup"><span data-stu-id="b52c7-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="b52c7-106">入力</span><span class="sxs-lookup"><span data-stu-id="b52c7-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="b52c7-107">フェーズ: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="b52c7-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="b52c7-108">部分的な反射のフェーズ</span><span class="sxs-lookup"><span data-stu-id="b52c7-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="b52c7-109">stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="b52c7-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="b52c7-110">開始状態を準備する oracle $A $ のユニタリ</span><span class="sxs-lookup"><span data-stu-id="b52c7-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="b52c7-111">idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b52c7-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b52c7-112">フラグ qubit へのインデックス</span><span class="sxs-lookup"><span data-stu-id="b52c7-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="b52c7-113">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="b52c7-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b52c7-114">部分的な反射によって実装される、oracles による振幅増幅を実装する操作。</span><span class="sxs-lookup"><span data-stu-id="b52c7-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="b52c7-115">解説</span><span class="sxs-lookup"><span data-stu-id="b52c7-115">Remarks</span></span>

<span data-ttu-id="b52c7-116">これにより、の開始と送信先の状態の形式に対してより厳密な条件が課さ `AmpAmpByReflectionPhases` れます。</span><span class="sxs-lookup"><span data-stu-id="b52c7-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="b52c7-117">ターゲットの状態が $ \ket f $ によってマークされていることを前提としてい {1} \_ ます。</span><span class="sxs-lookup"><span data-stu-id="b52c7-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="b52c7-118">\Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} \_ s + \sqrt{1-| \ ラムダ | ^ 2} \ket \end{align} \ket | \ lambda | ^ 2} \ket {0} \_ (ほとんどの場合、) は、 `flagQubit` `auxiliaryRegister` $ {0} \_ {f} s $ の状態で初期化さ {0} \_ れることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b52c7-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>