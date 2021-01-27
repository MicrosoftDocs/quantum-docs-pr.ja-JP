---
uid: Microsoft.Quantum.Synthesis.FlipMasks
title: FlipMasks 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FlipMasks
qsharp.summary: For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate. For convenience prepends result with 0.
ms.openlocfilehash: ca0ce69b3353379a42cc109cebb32efe4e364825
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859203"
---
# <a name="flipmasks-function"></a><span data-ttu-id="065bc-102">FlipMasks 関数</span><span class="sxs-lookup"><span data-stu-id="065bc-102">FlipMasks function</span></span>

<span data-ttu-id="065bc-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="065bc-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="065bc-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="065bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="065bc-105">2レベルのすべての列では、"フリップマスク" を計算します。これは、対応する 1-qubits ゲートを適用する前と後の逆にする必要がある qubits を表します。</span><span class="sxs-lookup"><span data-stu-id="065bc-105">For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate.</span></span>
<span data-ttu-id="065bc-106">便宜上、便宜のために0を使用します。</span><span class="sxs-lookup"><span data-stu-id="065bc-106">For convenience prepends result with 0.</span></span>

```qsharp
function FlipMasks (decomposition : (Microsoft.Quantum.Math.Complex[][], Int, Int)[], allQubitsMask : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="065bc-107">入力</span><span class="sxs-lookup"><span data-stu-id="065bc-107">Input</span></span>

### <a name="decomposition--complexintint"></a><span data-ttu-id="065bc-108">分解: ([Complex](xref:Microsoft.Quantum.Math.Complex)[] []、[int](xref:microsoft.quantum.lang-ref.int)、[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="065bc-108">decomposition : ([Complex](xref:Microsoft.Quantum.Math.Complex)[][],[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>




### <a name="allqubitsmask--int"></a><span data-ttu-id="065bc-109">allQubitsMask: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="065bc-109">allQubitsMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="065bc-110">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="065bc-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

