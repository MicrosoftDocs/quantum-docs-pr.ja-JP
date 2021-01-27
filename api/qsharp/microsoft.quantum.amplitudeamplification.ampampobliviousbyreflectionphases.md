---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpObliviousByReflectionPhases
title: AmpAmpObliviousByReflectionPhases 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpObliviousByReflectionPhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpObliviousByReflectionPhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromPartialReflections> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfrompartialreflections".
ms.openlocfilehash: c20c84195f84e759a6332a3c8689daa0fe23c6e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846733"
---
# <a name="ampampobliviousbyreflectionphases-function"></a><span data-ttu-id="e03a3-102">AmpAmpObliviousByReflectionPhases 関数</span><span class="sxs-lookup"><span data-stu-id="e03a3-102">AmpAmpObliviousByReflectionPhases function</span></span>

<span data-ttu-id="e03a3-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e03a3-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e03a3-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e03a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="e03a3-105">AmpAmpObliviousByReflectionPhases は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="e03a3-105">AmpAmpObliviousByReflectionPhases has been deprecated.</span></span> <span data-ttu-id="e03a3-106">代わりに、<xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromPartialReflections> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="e03a3-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromPartialReflections> instead.</span></span>
>
> <span data-ttu-id="e03a3-107">@"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfrompartialreflections" を使用してください。</span><span class="sxs-lookup"><span data-stu-id="e03a3-107">Please use @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfrompartialreflections".</span></span>



```qsharp
function AmpAmpObliviousByReflectionPhases (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="e03a3-108">入力</span><span class="sxs-lookup"><span data-stu-id="e03a3-108">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="e03a3-109">フェーズ: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="e03a3-109">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="e03a3-110">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="e03a3-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="e03a3-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="e03a3-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="e03a3-112">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="e03a3-112">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>





## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="e03a3-113">出力: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="e03a3-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

