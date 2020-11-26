---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196363"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="c9e57-102">InferredLabels 関数</span><span class="sxs-lookup"><span data-stu-id="c9e57-102">InferredLabels function</span></span>

<span data-ttu-id="c9e57-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c9e57-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c9e57-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c9e57-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="c9e57-105">分類確率の配列とバイアスを指定すると、各確率から推論されたラベルが返されます。</span><span class="sxs-lookup"><span data-stu-id="c9e57-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="c9e57-106">入力</span><span class="sxs-lookup"><span data-stu-id="c9e57-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="c9e57-107">バイアス: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c9e57-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c9e57-108">2つのクラス間のバイアス (通常は分類器のトレーニングの結果)。</span><span class="sxs-lookup"><span data-stu-id="c9e57-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="c9e57-109">確率: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c9e57-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c9e57-110">一連のサンプルの分類確率の配列。通常は、分類の頻度を推定した結果として得られます。</span><span class="sxs-lookup"><span data-stu-id="c9e57-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="c9e57-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c9e57-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c9e57-112">各分類確率から推論されるラベル。</span><span class="sxs-lookup"><span data-stu-id="c9e57-112">The label inferred from each classification probability.</span></span>