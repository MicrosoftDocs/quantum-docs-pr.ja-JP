---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 6e601cfd867b449d628da7cd60dfacd465e48860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191195"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="34c54-102">RotationPhasesAsReflectionPhases 関数</span><span class="sxs-lookup"><span data-stu-id="34c54-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="34c54-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="34c54-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="34c54-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34c54-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34c54-105">シングル qubit 回転として指定されたフェーズを部分反射として指定されたフェーズに変換します。</span><span class="sxs-lookup"><span data-stu-id="34c54-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="34c54-106">入力</span><span class="sxs-lookup"><span data-stu-id="34c54-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="34c54-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="34c54-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="34c54-108">部分的な反射に変換される単一の qubit 回転の配列。</span><span class="sxs-lookup"><span data-stu-id="34c54-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="34c54-109">出力: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="34c54-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="34c54-110">部分的な反射として指定されたフェーズを実装する操作。</span><span class="sxs-lookup"><span data-stu-id="34c54-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="34c54-111">リファレンス</span><span class="sxs-lookup"><span data-stu-id="34c54-111">References</span></span>

<span data-ttu-id="34c54-112">では、次の規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="34c54-112">We use the convention in</span></span>

- <span data-ttu-id="34c54-113">[ *G.H. Low, 語、*](https://arxiv.org/abs/1707.05391) 単一の qubit 回転フェーズをリフレクション演算子のフェーズに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="34c54-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>