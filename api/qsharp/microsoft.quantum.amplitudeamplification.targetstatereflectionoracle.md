---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: a6ed0397be57ef6f14a712749cc416e1fd98b71c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721725"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="a5750-102">TargetStateReflectionOracle 関数</span><span class="sxs-lookup"><span data-stu-id="a5750-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="a5750-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="a5750-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="a5750-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5750-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5750-105">`ReflectionOracle`フラグ qubit で一意にマークされたターゲット状態に関するを構築します。</span><span class="sxs-lookup"><span data-stu-id="a5750-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="a5750-106">ターゲット状態では、1つの qubit が1に設定され、それ以外の場合は 0: $ \ket {1} _f $ になります。</span><span class="sxs-lookup"><span data-stu-id="a5750-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="a5750-107">入力</span><span class="sxs-lookup"><span data-stu-id="a5750-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="a5750-108">idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a5750-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a5750-109">Oracle のフラグ qubit $f $ にインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5750-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="a5750-110">出力: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="a5750-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="a5750-111">`ReflectionOracle`$ \Ket _f $ によってマークされた状態に関する情報を反映する {1} 。</span><span class="sxs-lookup"><span data-stu-id="a5750-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5750-112">参照</span><span class="sxs-lookup"><span data-stu-id="a5750-112">See Also</span></span>

- [<span data-ttu-id="a5750-113">Microsoft. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="a5750-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)