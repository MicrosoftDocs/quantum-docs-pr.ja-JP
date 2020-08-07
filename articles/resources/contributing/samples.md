---
title: Microsoft QDK に貢献するサンプル
description: Microsoft Quantum Development Kit (QDK) にサンプルコードを投稿する方法について説明します。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: 20da0e1765a242c172cc595f03d7791a0e8b8d2d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867514"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="15d9a-103">Quantum 開発キットに貢献するサンプル</span><span class="sxs-lookup"><span data-stu-id="15d9a-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="15d9a-104">[サンプルリポジトリ](https://github.com/Microsoft/Quantum)にコードを投稿することに関心がある場合は、quantum 開発コミュニティをより良い場所にしていただき、ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="15d9a-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="15d9a-105">Quantum 開発キットのサンプルリポジトリ</span><span class="sxs-lookup"><span data-stu-id="15d9a-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="15d9a-106">できる限り多くの情報を提供するための貢献を準備するには、サンプルリポジトリがどのようにレイアウトされているかを簡単に確認してください。</span><span class="sxs-lookup"><span data-stu-id="15d9a-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

<span data-ttu-id="15d9a-107">つまり、 [microsoft/Quantum リポジトリ](https://github.com/microsoft/Quantum)のサンプルは、サブジェクト領域によって、、、などの別のフォルダーに分割され `algorithms/` `arithmetic/` `characterization/` ます。</span><span class="sxs-lookup"><span data-stu-id="15d9a-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="15d9a-108">各サブジェクト領域のフォルダー内では、各サンプルは1つのフォルダーで構成され、ユーザーがそのサンプルを調査して使用するために必要なすべてのものを収集します。</span><span class="sxs-lookup"><span data-stu-id="15d9a-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="15d9a-109">サンプルの構造化方法</span><span class="sxs-lookup"><span data-stu-id="15d9a-109">How Samples are Structured</span></span>

<span data-ttu-id="15d9a-110">各フォルダーを構成するファイルについては、「」のサンプルを参照して [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) ください。</span><span class="sxs-lookup"><span data-stu-id="15d9a-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="15d9a-111">ファイル</span><span class="sxs-lookup"><span data-stu-id="15d9a-111">File</span></span>              | <span data-ttu-id="15d9a-112">説明</span><span class="sxs-lookup"><span data-stu-id="15d9a-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="15d9a-113">Q#.NET Core SDK を使用してサンプルをビルドするために使用されるプロジェクト</span><span class="sxs-lookup"><span data-stu-id="15d9a-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="15d9a-114">Q#サンプルの操作と関数</span><span class="sxs-lookup"><span data-stu-id="15d9a-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="15d9a-115">サンプルを実行するために使用される C# ホストプログラム</span><span class="sxs-lookup"><span data-stu-id="15d9a-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="15d9a-116">サンプルを実行するために使用される Python ホストプログラム</span><span class="sxs-lookup"><span data-stu-id="15d9a-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="15d9a-117">サンプルの動作と使用方法に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="15d9a-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="15d9a-118">すべてのサンプルがまったく同じファイルセットを持つわけではありません (たとえば、一部のサンプルは C# のみである場合や、Python ホストを持っていない場合もあれば、補助データファイルを使用する必要があるサンプルもあります)。</span><span class="sxs-lookup"><span data-stu-id="15d9a-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="15d9a-119">役に立つ README ファイルの構造</span><span class="sxs-lookup"><span data-stu-id="15d9a-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="15d9a-120">ただし、特に重要なファイルとし `README.md` て、サンプルの使用を開始するためにユーザーが必要とするファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="15d9a-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="15d9a-121">各 `README.md` は、docs.microsoft.com/samples の投稿を見つけるのに役立ついくつかのメタデータから始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="15d9a-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="15d9a-122">Chsh ゲームのサンプルのレンダリング方法を確認する</span><span class="sxs-lookup"><span data-stu-id="15d9a-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="15d9a-123">このメタデータは、サンプル[YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header)で使用されている言語 (通常は、、、 `qsharp` `csharp` および `python` ) と、サンプルによってカバーされる製品 (通常は) を示す yaml ヘッダーとして提供され `qdk` ます。</span><span class="sxs-lookup"><span data-stu-id="15d9a-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="15d9a-124">`page_type: sample`サンプルを docs.microsoft.com/samples に表示するには、ヘッダー内のキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="15d9a-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="15d9a-125">同様に、 `product` との `language` キーは、ユーザーがサンプルを検索して実行できるようにするうえで重要です。</span><span class="sxs-lookup"><span data-stu-id="15d9a-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="15d9a-126">その後、新しいサンプルについて説明する短い概要を提供すると便利です。</span><span class="sxs-lookup"><span data-stu-id="15d9a-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="15d9a-127">また、サンプルのユーザーは、実行する必要があることを把握することもできます (たとえば、ユーザーが Quantum 開発キット自体を必要とするか、node.js などの追加ソフトウェアが必要なのでしょうか)。</span><span class="sxs-lookup"><span data-stu-id="15d9a-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="15d9a-128">そのすべてを使用して、サンプルを実行する方法をユーザーに伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="15d9a-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="15d9a-129">最後に、サンプル内の各ファイルについて、さらに詳細な情報を入手できる場所をユーザーに通知すると便利です。</span><span class="sxs-lookup"><span data-stu-id="15d9a-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="15d9a-130">ここでは絶対 Url を使用してください。サンプルは docs.microsoft.com/samples でレンダリングされるときに別の URL に表示されるためです。</span><span class="sxs-lookup"><span data-stu-id="15d9a-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
