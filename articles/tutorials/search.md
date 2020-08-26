---
title: 量子開発キットで Grover の検索アルゴリズムを実行する Q#
description: Q#標準のクォンタムアルゴリズムの1つである Grover のアルゴリズムを示すプロジェクトをビルドします。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
no-loc:
- Q#
- $$v
ms.openlocfilehash: f2ae56bdca893e8a317c16d0a993da15b9f021b5
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863118"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="cea8a-103">チュートリアル:Q\# でグローバーの検索アルゴリズムを実装する</span><span class="sxs-lookup"><span data-stu-id="cea8a-103">Tutorial: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="cea8a-104">このチュートリアルでは、グローバーの検索を構築して実行し、非構造化データの検索速度を上げる方法について学習できます。</span><span class="sxs-lookup"><span data-stu-id="cea8a-104">In this tutorial, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="cea8a-105">Grover の検索は最も一般的なクォンタムコンピューティングアルゴリズムの1つであり、この比較的小規模な実装では、クォンタム Q# Q# アルゴリズムを表現するために、高レベルのクォンタムプログラミング言語でクォンタムソリューションをプログラミングする利点の一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="cea8a-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="cea8a-106">このガイドの最後に、シミュレーションの出力があります。そこでは、従来のコンピューターでリスト全体を検索するのにかかる時間に比べてほんのわずかな時間で、順序付けられていないエントリのリストから特定の文字列の検索に成功することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cea8a-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="cea8a-107">グローバーのアルゴリズムでは、特定の項目の非構造化データのリストが検索されます。</span><span class="sxs-lookup"><span data-stu-id="cea8a-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="cea8a-108">たとえば、次のような質問に回答できます。一組のトランプから引いたこのカードは、ハートのエースですか?</span><span class="sxs-lookup"><span data-stu-id="cea8a-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="cea8a-109">特定の項目のラベル付けは、"_マークされた入力_" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="cea8a-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="cea8a-110">グローバーの検索アルゴリズムを使用すると、量子コンピューターで、探しているリスト内の項目数よりも少ない手順でこの検索が確実に実行されます。これは、従来のアルゴリズムでは実行できません。</span><span class="sxs-lookup"><span data-stu-id="cea8a-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="cea8a-111">一組のトランプの場合、速度の向上はごくわずかですが、数百万または数十億の項目が含まれるリストでは、大きな差が出ます。</span><span class="sxs-lookup"><span data-stu-id="cea8a-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="cea8a-112">数行のコードを記述するだけで、グローバーの検索アルゴリズムを構築できます。</span><span class="sxs-lookup"><span data-stu-id="cea8a-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cea8a-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="cea8a-113">Prerequisites</span></span>

- <span data-ttu-id="cea8a-114">Microsoft [Quantum 開発キット][install]。</span><span class="sxs-lookup"><span data-stu-id="cea8a-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="cea8a-115">グローバーの検索アルゴリズムで何ができるか</span><span class="sxs-lookup"><span data-stu-id="cea8a-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="cea8a-116">グローバーのアルゴリズムでは、リスト内の項目が探している項目かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="cea8a-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="cea8a-117">これは、各係数または確率振幅を使ってリストのインデックスの量子重ね合わせを構築し、その特定のインデックスが探しているものである確率を表すことで行います。</span><span class="sxs-lookup"><span data-stu-id="cea8a-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="cea8a-118">アルゴリズムは主に 2 つの手順から成ります。手順では、検索対象のインデックスの係数を、その係数の確率振幅が検索対象になるまで段階的に増やします。</span><span class="sxs-lookup"><span data-stu-id="cea8a-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="cea8a-119">増分ブーストの数は、リスト内の項目数より少なくなります。</span><span class="sxs-lookup"><span data-stu-id="cea8a-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="cea8a-120">これが、グローバーの検索アルゴリズムの手順が従来のアルゴリズムの手順より少ない理由です。</span><span class="sxs-lookup"><span data-stu-id="cea8a-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![グローバーの検索アルゴリズムの機能図](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="cea8a-122">コードを作成する</span><span class="sxs-lookup"><span data-stu-id="cea8a-122">Write the code</span></span>

1. <span data-ttu-id="cea8a-123">Quantum Development Kit を使用して、 [ Q# アプリケーションの新しいプロジェクトを作成](xref:microsoft.quantum.install.standalone)します。</span><span class="sxs-lookup"><span data-stu-id="cea8a-123">Using the Quantum Development Kit, [create a new Q# project for the application](xref:microsoft.quantum.install.standalone).</span></span> <span data-ttu-id="cea8a-124">プロジェクトに `Grover` というタイトルを付けます。</span><span class="sxs-lookup"><span data-stu-id="cea8a-124">Title the project `Grover`.</span></span>

1. <span data-ttu-id="cea8a-125">新しいプロジェクトで次のコードを `Program.qs` ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="cea8a-125">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="cea8a-126">検索するリストを定義するために、新しいファイル `Reflections.qs` を作成し、次のコードに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cea8a-126">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="cea8a-127">`ReflectAboutMarked` 操作では、検索対象としてマークが付けられた入力を定義します。これは、0 と 1 の交互の文字列です。</span><span class="sxs-lookup"><span data-stu-id="cea8a-127">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="cea8a-128">このサンプルにより、マークされた入力はハードコードされます。サンプルは他の入力を検索するために拡張したり、任意の入力用に一般化したりできます。</span><span class="sxs-lookup"><span data-stu-id="cea8a-128">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="cea8a-129">次に、新しいプログラムを実行し Q# て、でマークされた項目を検索し `ReflectAboutMarked` ます。</span><span class="sxs-lookup"><span data-stu-id="cea8a-129">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="cea8a-130">Q# Visual Studio または Visual Studio Code を使用したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="cea8a-130">Q# applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="cea8a-131">実行可能ファイルは、プロジェクトの構成とコマンドライン オプションに応じて、シミュレーターまたはリソース推定機能で `@EntryPoint()` 属性でマークされた操作または関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="cea8a-131">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="cea8a-132">Visual Studio では、Ctrl キーを押しながら F5 キーを押すだけでスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="cea8a-132">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="cea8a-133">VS Code では、ターミナルで次のように入力して、`Program.qs` の初回のビルドを行います。</span><span class="sxs-lookup"><span data-stu-id="cea8a-133">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="cea8a-134">以降の実行では、再度ビルドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cea8a-134">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="cea8a-135">これを実行するには、次のコマンドを入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cea8a-135">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="cea8a-136">ターミナルに次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cea8a-136">You should see the following message displayed in the terminal:</span></span>

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

<span data-ttu-id="cea8a-137">これは、使用するキュービットの数を指定しなかったためです。そのため、実行可能ファイルで使用できるコマンドがターミナルによって示されます。</span><span class="sxs-lookup"><span data-stu-id="cea8a-137">This is because you didn't specify the number of qubits you wanted to use, so the terminal tells you the commands available for the executable.</span></span> <span data-ttu-id="cea8a-138">5 つのキュービットを使用する場合は、次のように入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cea8a-138">If we want to use 5 qubits we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="cea8a-139">Enter キーを押すと、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cea8a-139">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="cea8a-140">次のステップ</span><span class="sxs-lookup"><span data-stu-id="cea8a-140">Next steps</span></span>

<span data-ttu-id="cea8a-141">このチュートリアルを楽しんでいる場合は、以下のリソースを参照して、を使用して Q# 独自の quantum アプリケーションを作成する方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="cea8a-141">If you enjoyed this tutorial, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="cea8a-142">QDK 入門ガイドに戻る</span><span class="sxs-lookup"><span data-stu-id="cea8a-142">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="cea8a-143">より一般的なグローバーの検索アルゴリズムの[サンプル](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)を試す</span><span class="sxs-lookup"><span data-stu-id="cea8a-143">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="cea8a-144">グローバーの検索と Quantum Katas について学習する</span><span class="sxs-lookup"><span data-stu-id="cea8a-144">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="cea8a-145">グローバーの検索アルゴリズムの背後にある量子コンピューティング手法である[振幅増幅][amplitude-amplification]について読む</span><span class="sxs-lookup"><span data-stu-id="cea8a-145">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="cea8a-146">量子コンピューティングの概念</span><span class="sxs-lookup"><span data-stu-id="cea8a-146">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="cea8a-147">Quantum 開発キット サンプル</span><span class="sxs-lookup"><span data-stu-id="cea8a-147">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
