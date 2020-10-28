---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: fc7c2c0d05ea626f7f7e5d8ebf3ce5ecea61390b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721949"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="2b36a-102">AmplitudeAmplificationFromPartialReflections 関数</span><span class="sxs-lookup"><span data-stu-id="2b36a-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="2b36a-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="2b36a-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="2b36a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b36a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b36a-105">部分的な反射による振幅増幅。</span><span class="sxs-lookup"><span data-stu-id="2b36a-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="2b36a-106">入力</span><span class="sxs-lookup"><span data-stu-id="2b36a-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="2b36a-107">フェーズ: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="2b36a-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="2b36a-108">部分的な反射のフェーズ</span><span class="sxs-lookup"><span data-stu-id="2b36a-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="2b36a-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="2b36a-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="2b36a-110">開始状態に関するリフレクション演算子</span><span class="sxs-lookup"><span data-stu-id="2b36a-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="2b36a-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="2b36a-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="2b36a-112">対象の状態に関するリフレクション演算子</span><span class="sxs-lookup"><span data-stu-id="2b36a-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="2b36a-113">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="2b36a-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2b36a-114">部分的な反射による振幅増幅を実装する操作。</span><span class="sxs-lookup"><span data-stu-id="2b36a-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b36a-115">解説</span><span class="sxs-lookup"><span data-stu-id="2b36a-115">Remarks</span></span>

<span data-ttu-id="2b36a-116">振幅増幅は、システム qubits がなく、無関係 oracle が id に設定されている無関係の振幅増幅の特殊なケースです。</span><span class="sxs-lookup"><span data-stu-id="2b36a-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="2b36a-117">ほとんどの場合、 `startQubits` は、 \_ の $-$1 eigenstate という状態で、$ \ket{\text{start}} $1 状態で初期化され `startStateReflection` ます。</span><span class="sxs-lookup"><span data-stu-id="2b36a-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>