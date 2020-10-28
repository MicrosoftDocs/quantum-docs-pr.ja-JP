---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpByOraclePhases
title: AmpAmpByOraclePhases 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpByOraclePhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpByOraclePhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfromstatepreparation".
ms.openlocfilehash: e45b6b0fdb3aa9a9c0a934e09e1aabd4ea42e0cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720079"
---
# <a name="ampampbyoraclephases-function"></a><span data-ttu-id="2052e-102">AmpAmpByOraclePhases 関数</span><span class="sxs-lookup"><span data-stu-id="2052e-102">AmpAmpByOraclePhases function</span></span>

<span data-ttu-id="2052e-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="2052e-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="2052e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2052e-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="2052e-105">AmpAmpByOraclePhases は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="2052e-105">AmpAmpByOraclePhases has been deprecated.</span></span> <span data-ttu-id="2052e-106">代わりに、<xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="2052e-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation> instead.</span></span>
>
> <span data-ttu-id="2052e-107">@"microsoft.quantum.amplitudeamplification.amplitudeamplificationfromstatepreparation" を使用してください。</span><span class="sxs-lookup"><span data-stu-id="2052e-107">Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfromstatepreparation".</span></span>



```qsharp
function AmpAmpByOraclePhases (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="2052e-108">入力</span><span class="sxs-lookup"><span data-stu-id="2052e-108">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="2052e-109">フェーズ: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="2052e-109">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="stateoracle--stateoracle"></a><span data-ttu-id="2052e-110">stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="2052e-110">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>




### <a name="idxflagqubit--int"></a><span data-ttu-id="2052e-111">idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2052e-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="2052e-112">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="2052e-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

