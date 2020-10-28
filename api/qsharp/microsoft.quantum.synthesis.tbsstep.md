---
uid: Microsoft.Quantum.Synthesis.TBSStep
title: TBSStep 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TBSStep
qsharp.summary: Computes gate masks to transform perm[x] to x and updates the current permutation.
ms.openlocfilehash: b33269afc2ac14106a18a09e855a8d067b9c558b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725449"
---
# <a name="tbsstep-function"></a><span data-ttu-id="03327-102">TBSStep 関数</span><span class="sxs-lookup"><span data-stu-id="03327-102">TBSStep function</span></span>

<span data-ttu-id="03327-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="03327-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="03327-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="03327-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="03327-105">[X] を x に変換し、現在の順列を更新するゲートマスクを計算します。</span><span class="sxs-lookup"><span data-stu-id="03327-105">Computes gate masks to transform perm[x] to x and updates the current permutation.</span></span>

```qsharp
function TBSStep (state : (Int[], Microsoft.Quantum.Synthesis.MCMTMask[]), x : Int) : (Int[], Microsoft.Quantum.Synthesis.MCMTMask[])
```


## <a name="input"></a><span data-ttu-id="03327-106">入力</span><span class="sxs-lookup"><span data-stu-id="03327-106">Input</span></span>

### <a name="state--intmcmtmask"></a><span data-ttu-id="03327-107">状態: ([Int](xref:microsoft.quantum.lang-ref.int)[]、[Mcmtmask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span><span class="sxs-lookup"><span data-stu-id="03327-107">state : ([Int](xref:microsoft.quantum.lang-ref.int)[],[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span></span>




### <a name="x--int"></a><span data-ttu-id="03327-108">x: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03327-108">x : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intmcmtmask"></a><span data-ttu-id="03327-109">出力: ([Int](xref:microsoft.quantum.lang-ref.int)[]、[Mcmtmask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span><span class="sxs-lookup"><span data-stu-id="03327-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int)[],[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span></span>

