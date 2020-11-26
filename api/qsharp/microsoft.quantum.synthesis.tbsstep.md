---
uid: Microsoft.Quantum.Synthesis.TBSStep
title: TBSStep 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TBSStep
qsharp.summary: Computes gate masks to transform perm[x] to x and updates the current permutation.
ms.openlocfilehash: 272ab3221e02127074fe6bfc65aee47c40eb88b5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231060"
---
# <a name="tbsstep-function"></a><span data-ttu-id="85d6d-102">TBSStep 関数</span><span class="sxs-lookup"><span data-stu-id="85d6d-102">TBSStep function</span></span>

<span data-ttu-id="85d6d-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="85d6d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="85d6d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85d6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85d6d-105">[X] を x に変換し、現在の順列を更新するゲートマスクを計算します。</span><span class="sxs-lookup"><span data-stu-id="85d6d-105">Computes gate masks to transform perm[x] to x and updates the current permutation.</span></span>

```qsharp
function TBSStep (state : (Int[], Microsoft.Quantum.Synthesis.MCMTMask[]), x : Int) : (Int[], Microsoft.Quantum.Synthesis.MCMTMask[])
```


## <a name="input"></a><span data-ttu-id="85d6d-106">入力</span><span class="sxs-lookup"><span data-stu-id="85d6d-106">Input</span></span>

### <a name="state--intmcmtmask"></a><span data-ttu-id="85d6d-107">状態: ([Int](xref:microsoft.quantum.lang-ref.int)[]、[Mcmtmask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span><span class="sxs-lookup"><span data-stu-id="85d6d-107">state : ([Int](xref:microsoft.quantum.lang-ref.int)[],[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span></span>




### <a name="x--int"></a><span data-ttu-id="85d6d-108">x: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="85d6d-108">x : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intmcmtmask"></a><span data-ttu-id="85d6d-109">出力: ([Int](xref:microsoft.quantum.lang-ref.int)[]、[Mcmtmask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span><span class="sxs-lookup"><span data-stu-id="85d6d-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int)[],[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span></span>

