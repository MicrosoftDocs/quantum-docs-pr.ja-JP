---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 6ddb48ba66eea87a07d515ff791bfb34f2d98b76
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856831"
---
# <a name="purifiedmixedstaterequirements-function"></a><span data-ttu-id="023de-102">PurifiedMixedStateRequirements 関数</span><span class="sxs-lookup"><span data-stu-id="023de-102">PurifiedMixedStateRequirements function</span></span>

<span data-ttu-id="023de-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="023de-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="023de-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="023de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="023de-105">によって返された操作を適用するために割り当てる必要がある qubits の合計数を返し @"microsoft.quantum.preparation.purifiedmixedstate" ます。</span><span class="sxs-lookup"><span data-stu-id="023de-105">Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".</span></span>

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a><span data-ttu-id="023de-106">入力</span><span class="sxs-lookup"><span data-stu-id="023de-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="023de-107">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="023de-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="023de-108">ターゲットエラー $ \ イプシロン $。</span><span class="sxs-lookup"><span data-stu-id="023de-108">The target error $\epsilon$.</span></span>


### <a name="ncoefficients--int"></a><span data-ttu-id="023de-109">n 係数: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="023de-109">nCoefficients : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="023de-110">混合状態を準備するときに指定する係数の数。</span><span class="sxs-lookup"><span data-stu-id="023de-110">The number of coefficients to be specified in preparing a mixed state.</span></span>



## <a name="output--mixedstatepreparationrequirements"></a><span data-ttu-id="023de-111">出力: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="023de-111">Output : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>

<span data-ttu-id="023de-112">合計で必要とされる qubits の数、および関数によって使用される各インデックスとガベージレジスタについての説明 @"microsoft.quantum.preparation.purifiedmixedstate" 。</span><span class="sxs-lookup"><span data-stu-id="023de-112">A description of how many qubits are required in total, and for each of the index and garbage registers used by the @"microsoft.quantum.preparation.purifiedmixedstate" function.</span></span>

## <a name="see-also"></a><span data-ttu-id="023de-113">参照</span><span class="sxs-lookup"><span data-stu-id="023de-113">See Also</span></span>

- [<span data-ttu-id="023de-114">PurifiedMixedState の準備</span><span class="sxs-lookup"><span data-stu-id="023de-114">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)