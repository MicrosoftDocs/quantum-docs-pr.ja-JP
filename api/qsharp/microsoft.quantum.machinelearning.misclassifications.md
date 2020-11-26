---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: 誤分類関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211680"
---
# <a name="misclassifications-function"></a><span data-ttu-id="fc0ea-102">誤分類関数</span><span class="sxs-lookup"><span data-stu-id="fc0ea-102">Misclassifications function</span></span>

<span data-ttu-id="fc0ea-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="fc0ea-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="fc0ea-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="fc0ea-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="fc0ea-105">一連の推定ラベルと一連の正しいラベルが指定されている場合、ラベルの各セットが異なる場所のインデックスを返します。</span><span class="sxs-lookup"><span data-stu-id="fc0ea-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="fc0ea-106">入力</span><span class="sxs-lookup"><span data-stu-id="fc0ea-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="fc0ea-107">inferredLabels: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fc0ea-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fc0ea-108">特定のトレーニングまたは検証セットに対して推論されるラベル。</span><span class="sxs-lookup"><span data-stu-id="fc0ea-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="fc0ea-109">actualLabels: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fc0ea-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fc0ea-110">指定されたトレーニングまたは検証セットの真のラベル。</span><span class="sxs-lookup"><span data-stu-id="fc0ea-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="fc0ea-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fc0ea-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fc0ea-112">などのインデックスの配列 `idx` `inferredLabels[idx] != actualLabels[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="fc0ea-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>