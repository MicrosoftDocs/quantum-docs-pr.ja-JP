---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722518"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="22723-102">InferredLabel 関数</span><span class="sxs-lookup"><span data-stu-id="22723-102">InferredLabel function</span></span>

<span data-ttu-id="22723-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="22723-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="22723-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22723-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22723-105">分類の確率とバイアスが指定されている場合、はその確率から推論されたラベルを返します。</span><span class="sxs-lookup"><span data-stu-id="22723-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="22723-106">入力</span><span class="sxs-lookup"><span data-stu-id="22723-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="22723-107">バイアス: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="22723-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="22723-108">2つのクラス間のバイアス (通常は分類器のトレーニングの結果)。</span><span class="sxs-lookup"><span data-stu-id="22723-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="22723-109">確率: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="22723-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="22723-110">特定のサンプルの分類確率。通常は、その分類頻度を推定した結果になります。</span><span class="sxs-lookup"><span data-stu-id="22723-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="22723-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="22723-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="22723-112">指定された分類確率から推論されるラベル。</span><span class="sxs-lookup"><span data-stu-id="22723-112">The label inferred from the given classification probability.</span></span>