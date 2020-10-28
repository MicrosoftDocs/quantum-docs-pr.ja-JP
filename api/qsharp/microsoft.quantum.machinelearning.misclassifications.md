---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: 誤分類関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723582"
---
# <a name="misclassifications-function"></a><span data-ttu-id="93223-102">誤分類関数</span><span class="sxs-lookup"><span data-stu-id="93223-102">Misclassifications function</span></span>

<span data-ttu-id="93223-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="93223-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="93223-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93223-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93223-105">一連の推定ラベルと一連の正しいラベルが指定されている場合、ラベルの各セットが異なる場所のインデックスを返します。</span><span class="sxs-lookup"><span data-stu-id="93223-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="93223-106">入力</span><span class="sxs-lookup"><span data-stu-id="93223-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="93223-107">inferredLabels: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="93223-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="93223-108">特定のトレーニングまたは検証セットに対して推論されるラベル。</span><span class="sxs-lookup"><span data-stu-id="93223-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="93223-109">actualLabels: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="93223-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="93223-110">指定されたトレーニングまたは検証セットの真のラベル。</span><span class="sxs-lookup"><span data-stu-id="93223-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="93223-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="93223-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="93223-112">などのインデックスの配列 `idx` `inferredLabels[idx] != actualLabels[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="93223-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>