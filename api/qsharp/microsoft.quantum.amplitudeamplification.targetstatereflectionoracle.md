---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 4169ccf3e210e27f779311553b845ea04f2c7dc6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843905"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="8ba56-102">TargetStateReflectionOracle 関数</span><span class="sxs-lookup"><span data-stu-id="8ba56-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="8ba56-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="8ba56-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="8ba56-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ba56-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ba56-105">`ReflectionOracle`フラグ qubit で一意にマークされたターゲット状態に関するを構築します。</span><span class="sxs-lookup"><span data-stu-id="8ba56-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="8ba56-106">ターゲット状態では、1つの qubit が1に設定され、それ以外の場合は 0: $ \ket {1} _f $ になります。</span><span class="sxs-lookup"><span data-stu-id="8ba56-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="8ba56-107">入力</span><span class="sxs-lookup"><span data-stu-id="8ba56-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="8ba56-108">idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8ba56-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8ba56-109">Oracle のフラグ qubit $f $ にインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ba56-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="8ba56-110">出力: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="8ba56-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="8ba56-111">`ReflectionOracle`$ \Ket _f $ によってマークされた状態に関する情報を反映する {1} 。</span><span class="sxs-lookup"><span data-stu-id="8ba56-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ba56-112">参照</span><span class="sxs-lookup"><span data-stu-id="8ba56-112">See Also</span></span>

- [<span data-ttu-id="8ba56-113">Microsoft. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="8ba56-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)