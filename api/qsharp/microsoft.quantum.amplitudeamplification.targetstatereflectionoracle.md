---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 65ad316a6ac986ebd0dc28b25859026a60aa3239
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191110"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="f56bb-102">TargetStateReflectionOracle 関数</span><span class="sxs-lookup"><span data-stu-id="f56bb-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="f56bb-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="f56bb-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="f56bb-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f56bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f56bb-105">`ReflectionOracle`フラグ qubit で一意にマークされたターゲット状態に関するを構築します。</span><span class="sxs-lookup"><span data-stu-id="f56bb-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="f56bb-106">ターゲット状態では、1つの qubit が1に設定され、それ以外の場合は 0: $ \ket {1} _f $ になります。</span><span class="sxs-lookup"><span data-stu-id="f56bb-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="f56bb-107">入力</span><span class="sxs-lookup"><span data-stu-id="f56bb-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="f56bb-108">idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f56bb-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f56bb-109">Oracle のフラグ qubit $f $ にインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f56bb-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="f56bb-110">出力: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="f56bb-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="f56bb-111">`ReflectionOracle`$ \Ket _f $ によってマークされた状態に関する情報を反映する {1} 。</span><span class="sxs-lookup"><span data-stu-id="f56bb-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="f56bb-112">参照</span><span class="sxs-lookup"><span data-stu-id="f56bb-112">See Also</span></span>

- [<span data-ttu-id="f56bb-113">Microsoft. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="f56bb-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)