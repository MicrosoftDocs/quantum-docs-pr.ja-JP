---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848416"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="48fd7-102">InferredLabel 関数</span><span class="sxs-lookup"><span data-stu-id="48fd7-102">InferredLabel function</span></span>

<span data-ttu-id="48fd7-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="48fd7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="48fd7-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="48fd7-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="48fd7-105">分類の確率とバイアスが指定されている場合、はその確率から推論されたラベルを返します。</span><span class="sxs-lookup"><span data-stu-id="48fd7-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="48fd7-106">入力</span><span class="sxs-lookup"><span data-stu-id="48fd7-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="48fd7-107">バイアス: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="48fd7-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="48fd7-108">2つのクラス間のバイアス (通常は分類器のトレーニングの結果)。</span><span class="sxs-lookup"><span data-stu-id="48fd7-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="48fd7-109">確率: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="48fd7-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="48fd7-110">特定のサンプルの分類確率。通常は、その分類頻度を推定した結果になります。</span><span class="sxs-lookup"><span data-stu-id="48fd7-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="48fd7-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48fd7-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48fd7-112">指定された分類確率から推論されるラベル。</span><span class="sxs-lookup"><span data-stu-id="48fd7-112">The label inferred from the given classification probability.</span></span>