---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 5d50b3fdc2b0f948e93cb11b5c69403d97574ccd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843951"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="13e39-102">RotationPhasesAsReflectionPhases 関数</span><span class="sxs-lookup"><span data-stu-id="13e39-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="13e39-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="13e39-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="13e39-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13e39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13e39-105">シングル qubit 回転として指定されたフェーズを部分反射として指定されたフェーズに変換します。</span><span class="sxs-lookup"><span data-stu-id="13e39-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="13e39-106">入力</span><span class="sxs-lookup"><span data-stu-id="13e39-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="13e39-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="13e39-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="13e39-108">部分的な反射に変換される単一の qubit 回転の配列。</span><span class="sxs-lookup"><span data-stu-id="13e39-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="13e39-109">出力: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="13e39-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="13e39-110">部分的な反射として指定されたフェーズを実装する操作。</span><span class="sxs-lookup"><span data-stu-id="13e39-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="13e39-111">References</span><span class="sxs-lookup"><span data-stu-id="13e39-111">References</span></span>

<span data-ttu-id="13e39-112">では、次の規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="13e39-112">We use the convention in</span></span>

- <span data-ttu-id="13e39-113">[ *G.H. Low, 語、*](https://arxiv.org/abs/1707.05391) 単一の qubit 回転フェーズをリフレクション演算子のフェーズに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="13e39-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>