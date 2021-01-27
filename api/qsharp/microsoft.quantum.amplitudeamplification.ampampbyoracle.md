---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpByOracle
title: AmpAmpByOracle 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpByOracle
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpByOracle has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.standardamplitudeamplification".
ms.openlocfilehash: 27775b35523522298cbca5d6d1e3c36ea24acf97
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844014"
---
# <a name="ampampbyoracle-function"></a><span data-ttu-id="644ab-102">AmpAmpByOracle 関数</span><span class="sxs-lookup"><span data-stu-id="644ab-102">AmpAmpByOracle function</span></span>

<span data-ttu-id="644ab-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="644ab-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="644ab-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="644ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="644ab-105">AmpAmpByOracle は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="644ab-105">AmpAmpByOracle has been deprecated.</span></span> <span data-ttu-id="644ab-106">代わりに、<xref:Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="644ab-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification> instead.</span></span>
>
> <span data-ttu-id="644ab-107">@"microsoft.quantum.amplitudeamplification.standardamplitudeamplification" を使用してください。</span><span class="sxs-lookup"><span data-stu-id="644ab-107">Please use @"microsoft.quantum.amplitudeamplification.standardamplitudeamplification".</span></span>



```qsharp
function AmpAmpByOracle (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="644ab-108">入力</span><span class="sxs-lookup"><span data-stu-id="644ab-108">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="644ab-109">nIterations: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="644ab-109">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="stateoracle--stateoracle"></a><span data-ttu-id="644ab-110">stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="644ab-110">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>




### <a name="idxflagqubit--int"></a><span data-ttu-id="644ab-111">idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="644ab-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="644ab-112">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="644ab-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

