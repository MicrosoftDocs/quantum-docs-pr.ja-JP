---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpByOraclePhases
title: AmpAmpByOraclePhases 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpByOraclePhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpByOraclePhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfromstatepreparation".
ms.openlocfilehash: 2b602860fab36e175b90260289d1d81abff95765
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191807"
---
# <a name="ampampbyoraclephases-function"></a><span data-ttu-id="d8fc9-102">AmpAmpByOraclePhases 関数</span><span class="sxs-lookup"><span data-stu-id="d8fc9-102">AmpAmpByOraclePhases function</span></span>

<span data-ttu-id="d8fc9-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d8fc9-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d8fc9-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8fc9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="d8fc9-105">AmpAmpByOraclePhases は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="d8fc9-105">AmpAmpByOraclePhases has been deprecated.</span></span> <span data-ttu-id="d8fc9-106">代わりに、<xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="d8fc9-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation> instead.</span></span>
>
> <span data-ttu-id="d8fc9-107">@"microsoft.quantum.amplitudeamplification.amplitudeamplificationfromstatepreparation" を使用してください。</span><span class="sxs-lookup"><span data-stu-id="d8fc9-107">Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfromstatepreparation".</span></span>



```qsharp
function AmpAmpByOraclePhases (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="d8fc9-108">入力</span><span class="sxs-lookup"><span data-stu-id="d8fc9-108">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="d8fc9-109">フェーズ: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="d8fc9-109">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="stateoracle--stateoracle"></a><span data-ttu-id="d8fc9-110">stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="d8fc9-110">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>




### <a name="idxflagqubit--int"></a><span data-ttu-id="d8fc9-111">idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8fc9-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="d8fc9-112">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d8fc9-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

