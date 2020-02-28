---
title: 典型的データを読み込んでいます
description: Microsoft Quantum Development Kit (QDK) を使用して、独自のデータセットを読み込んで分類器モデルをトレーニングする方法について説明します。
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
ms.openlocfilehash: 15e63ced6223759a332ce22a43c133a7899f482a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909961"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="53978-103">独自のデータセットを読み込んで分類する</span><span class="sxs-lookup"><span data-stu-id="53978-103">Load and classify your own datasets</span></span>

<span data-ttu-id="53978-104">この短いチュートリアルでは、独自のデータセットを読み込んで、Quantum 開発キット (QDK) で分類器モデルをトレーニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="53978-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="53978-105">データの格納には、 [JSON ファイル](https://en.wikipedia.org/wiki/JSON)などの標準化されたシリアル化形式を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="53978-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="53978-106">このような形式では、Python や .NET エコシステムなどのさまざまなフレームワークとの高い互換性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="53978-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="53978-107">特に、サンプルから直接コードをコピーして貼り付けることができるように、データの読み込みにテンプレートを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="53978-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="53978-108">データセットを読み込むためのテンプレート</span><span class="sxs-lookup"><span data-stu-id="53978-108">Template for loading your datasets</span></span>

<span data-ttu-id="53978-109">$N = $2 のトレーニングデータセット $ (x, y) $ があるとします。この場合、$x $ の各インスタンス $x _i $ には、$x _ {i1} $、$x _ {i2} $、$x _ {i3} $ という3つの特徴があります。</span><span class="sxs-lookup"><span data-stu-id="53978-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="53978-110">検証データセットの構造は同じです。</span><span class="sxs-lookup"><span data-stu-id="53978-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="53978-111">これらの datsets は、次のような `data.json` ファイルで表すことができます。</span><span class="sxs-lookup"><span data-stu-id="53978-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a><span data-ttu-id="53978-112">テンプレートを使用した例</span><span class="sxs-lookup"><span data-stu-id="53978-112">Example using the template</span></span>

<span data-ttu-id="53978-113">さまざまな猫や犬の高さと重みを持つ小さなデータセットがあるとします。</span><span class="sxs-lookup"><span data-stu-id="53978-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="53978-114">このデータセットは、モデルのトレーニングには非常に小さなものですが、データセットを読み込むプロセスを示すのに十分です。</span><span class="sxs-lookup"><span data-stu-id="53978-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="53978-115">高さ (m)</span><span class="sxs-lookup"><span data-stu-id="53978-115">Height (m)</span></span> | <span data-ttu-id="53978-116">ウエイト (kg)</span><span class="sxs-lookup"><span data-stu-id="53978-116">Weight (kg)</span></span> | <span data-ttu-id="53978-117">動物</span><span class="sxs-lookup"><span data-stu-id="53978-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="53978-118">0.54</span><span class="sxs-lookup"><span data-stu-id="53978-118">0.54</span></span>      | <span data-ttu-id="53978-119">30</span><span class="sxs-lookup"><span data-stu-id="53978-119">30</span></span>         | <span data-ttu-id="53978-120">Dog</span><span class="sxs-lookup"><span data-stu-id="53978-120">Dog</span></span>    |
| <span data-ttu-id="53978-121">0.30</span><span class="sxs-lookup"><span data-stu-id="53978-121">0.30</span></span>      | <span data-ttu-id="53978-122">8</span><span class="sxs-lookup"><span data-stu-id="53978-122">8</span></span>          | <span data-ttu-id="53978-123">Cat</span><span class="sxs-lookup"><span data-stu-id="53978-123">Cat</span></span>    |
| <span data-ttu-id="53978-124">0.91</span><span class="sxs-lookup"><span data-stu-id="53978-124">0.91</span></span>      | <span data-ttu-id="53978-125">44</span><span class="sxs-lookup"><span data-stu-id="53978-125">44</span></span>         | <span data-ttu-id="53978-126">Dog</span><span class="sxs-lookup"><span data-stu-id="53978-126">Dog</span></span>    |
| <span data-ttu-id="53978-127">0.86</span><span class="sxs-lookup"><span data-stu-id="53978-127">0.86</span></span>      | <span data-ttu-id="53978-128">31</span><span class="sxs-lookup"><span data-stu-id="53978-128">31</span></span>          | <span data-ttu-id="53978-129">Dog</span><span class="sxs-lookup"><span data-stu-id="53978-129">Dog</span></span>    |
| <span data-ttu-id="53978-130">0.32</span><span class="sxs-lookup"><span data-stu-id="53978-130">0.32</span></span>      | <span data-ttu-id="53978-131">5</span><span class="sxs-lookup"><span data-stu-id="53978-131">5</span></span>         | <span data-ttu-id="53978-132">Cat</span><span class="sxs-lookup"><span data-stu-id="53978-132">Cat</span></span>    |
| <span data-ttu-id="53978-133">0.25</span><span class="sxs-lookup"><span data-stu-id="53978-133">0.25</span></span>      | <span data-ttu-id="53978-134">4</span><span class="sxs-lookup"><span data-stu-id="53978-134">4</span></span>          | <span data-ttu-id="53978-135">Cat</span><span class="sxs-lookup"><span data-stu-id="53978-135">Cat</span></span>    |

<span data-ttu-id="53978-136">プロセスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="53978-136">The process is:</span></span>

- <span data-ttu-id="53978-137">まず、データセットをトレーニングと検証に分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53978-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="53978-138">このケースでは、最初の3つのサンプルでトレーニングを行い、残りのサンプルで検証を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="53978-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="53978-139">一般に、トレーニングデータの不要なバイアスを避けるために、トレーニングと検証のデータセットをランダムにサンプリングすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="53978-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="53978-140">次に、各クラスに数値ラベルを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="53978-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="53978-141">現時点では、QML ライブラリは二項分類の問題のみを使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="53978-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="53978-142">ここでは、ラベル0をクラス `Dog` に割り当て、番号1をクラス `Cat`に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="53978-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="53978-143">最後に、データセットのデータを使用して、テンプレートに入力します。</span><span class="sxs-lookup"><span data-stu-id="53978-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="53978-144">大規模なデータセットの場合は、特定のデータセットからテンプレートを自動的に生成するための小さなスクリプトを作成する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="53978-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="53978-145">このスクリプトは、データセットの元の形式によって異なります。</span><span class="sxs-lookup"><span data-stu-id="53978-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="53978-146">データセットの場合、`data.json` ファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="53978-146">For our dataset the `data.json` file is:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a><span data-ttu-id="53978-147">データを読み込んでいます</span><span class="sxs-lookup"><span data-stu-id="53978-147">Loading the data</span></span>

<span data-ttu-id="53978-148">データを JSON ファイルとしてシリアル化したら、選択したホスト言語で提供される JSON ライブラリを使用して、データを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="53978-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="53978-149">Python</span><span class="sxs-lookup"><span data-stu-id="53978-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="53978-150">Python には、JSON でシリアル化されたデータを操作するための[組み込みの `json` パッケージ](https://docs.python.org/3.7/library/json.html)が用意されています。</span><span class="sxs-lookup"><span data-stu-id="53978-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="53978-151">C#</span><span class="sxs-lookup"><span data-stu-id="53978-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="53978-152">.NET Core プラットフォームには、JSON でシリアル化されたデータを処理するための[`System.Text.Json` パッケージ](https://www.nuget.org/packages/System.Text.Json)が用意されています。</span><span class="sxs-lookup"><span data-stu-id="53978-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="whats-next"></a><span data-ttu-id="53978-153">次の操作</span><span class="sxs-lookup"><span data-stu-id="53978-153">What's next?</span></span>

<span data-ttu-id="53978-154">これで、独自のデータセットを使用して独自の実験の実行を開始する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="53978-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="53978-155">さまざまな分類子とデータセットを試し、結果を共有するコミュニティに投稿してください。</span><span class="sxs-lookup"><span data-stu-id="53978-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
