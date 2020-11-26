---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpByReflectionPhases
title: AmpAmpByReflectionPhases 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpByReflectionPhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpByReflectionPhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfrompartialreflections".
ms.openlocfilehash: 3cbb067aad75daf5c6807ce750e22da024eff44a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191773"
---
# <a name="ampampbyreflectionphases-function"></a><span data-ttu-id="f6c95-102">AmpAmpByReflectionPhases 関数</span><span class="sxs-lookup"><span data-stu-id="f6c95-102">AmpAmpByReflectionPhases function</span></span>

<span data-ttu-id="f6c95-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="f6c95-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="f6c95-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f6c95-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="f6c95-105">AmpAmpByReflectionPhases は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="f6c95-105">AmpAmpByReflectionPhases has been deprecated.</span></span> <span data-ttu-id="f6c95-106">代わりに、<xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="f6c95-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections> instead.</span></span>
>
> <span data-ttu-id="f6c95-107">@"microsoft.quantum.amplitudeamplification.amplitudeamplificationfrompartialreflections" を使用してください。</span><span class="sxs-lookup"><span data-stu-id="f6c95-107">Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfrompartialreflections".</span></span>



```qsharp
function AmpAmpByReflectionPhases (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="f6c95-108">入力</span><span class="sxs-lookup"><span data-stu-id="f6c95-108">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="f6c95-109">フェーズ: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="f6c95-109">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="f6c95-110">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="f6c95-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="f6c95-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="f6c95-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>





## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="f6c95-112">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="f6c95-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

