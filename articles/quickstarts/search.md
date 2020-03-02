---
title: Q# でグローバーの検索アルゴリズムを実行する - Quantum 開発キット
description: 正規の量子アルゴリズムの 1 つであるグローバーのアルゴリズムを示す Q# プロジェクトを構築します。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 0e64fcd56929fa33397c45bf1b2e99bf687eca6f
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906952"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="2fdbe-103">クイック スタート:Q# でグローバーの検索アルゴリズムを実装する</span><span class="sxs-lookup"><span data-stu-id="2fdbe-103">Quickstart: Implement Grover's search algorithm in Q#</span></span>

<span data-ttu-id="2fdbe-104">このクイック スタートでは、グローバーの検索を構築して実行子、非構造化データの検索速度を上げる方法について学習できます。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="2fdbe-105">グローバーの検索は、最も人気がある量子コンピューティング アルゴリズムの 1 つであり、この比較的小規模な Q# 実装で、量子ソリューションをプログラミングすることの利点のいくつかと、量子アルゴリズムを表わす Q# 量子プログラミング言語の概要が理解できます。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="2fdbe-106">ガイドの終わりには、シミュレーションの出力があります。この中で、旧式のコンピューターではリスト全体を検索するためにかかったであろう時間に比べ、ほんのわずかな時間で注文リストから特定の文字列を検索することに成功しています。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of onordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="2fdbe-107">グローバーのアルゴリズムでは、特定の項目の非構造化データのリストが検索されます。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="2fdbe-108">たとえば、次のような質問に回答できます。一組のトランプから引いたこのカードは、ハートのエースですか?</span><span class="sxs-lookup"><span data-stu-id="2fdbe-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="2fdbe-109">特定の項目のラベル付けは、"_マークされた入力_" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="2fdbe-110">グローバーの検索アルゴリズムを使用すると、量子コンピューターで、探しているリスト内の項目数よりも少ない手順でこの検索が確実に実行されます。これは、従来のアルゴリズムでは実行できません。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="2fdbe-111">一組のトランプの場合、速度の向上はごくわずかですが、数百万または数十億の項目が含まれるリストでは、大きな差が出ます。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="2fdbe-112">数行のコードを記述するだけで、グローバーの検索アルゴリズムを構築できます。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2fdbe-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="2fdbe-113">Prerequisites</span></span>

- <span data-ttu-id="2fdbe-114">Microsoft [Quantum 開発キット][install]。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="2fdbe-115">グローバーの検索アルゴリズムで何ができるか</span><span class="sxs-lookup"><span data-stu-id="2fdbe-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="2fdbe-116">グローバーのアルゴリズムでは、リスト内の項目が探している項目かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="2fdbe-117">これは、各係数または確率振幅を使ってリストのインデックスの量子重ね合わせを構築し、その特定のインデックスが探しているものである確率を表すことで行います。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="2fdbe-118">アルゴリズムは主に 2 つの手順から成ります。手順では、検索対象のインデックスの係数を、その係数の確率振幅が検索対象になるまで段階的に増やします。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="2fdbe-119">増分ブーストの数は、リスト内の項目数より少なくなります。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="2fdbe-120">これが、グローバーの検索アルゴリズムの手順が従来のアルゴリズムの手順より少ない理由です。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![グローバーの検索アルゴリズムの機能図](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="2fdbe-122">コードを作成する</span><span class="sxs-lookup"><span data-stu-id="2fdbe-122">Write the code</span></span>

1. <span data-ttu-id="2fdbe-123">Quantum 開発キットを使用して、任意の開発環境に `Grover` という[新しい Q# プロジェクトを作成](xref:microsoft.quantum.howto.createproject)します。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="2fdbe-124">新しいプロジェクトで次のコードを `Operations.qs` ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-124">Add the following code to the `Operations.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-40":::

1. <span data-ttu-id="2fdbe-125">検索するリストを定義するために、新しいファイル `Reflections.qs` を作成し、次のコードに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="2fdbe-126">`ReflectAboutMarked` 操作では、検索対象としてマークが付けられた入力を定義します。これは、0 と 1 の交互の文字列です。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="2fdbe-127">このサンプルにより、マークされた入力はハードコードされます。サンプルは他の入力を検索するために拡張したり、任意の入力用に一般化したりできます。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="2fdbe-128">次に、新しい Q# プログラムを実行して、`ReflectAboutMarked` によってマークされた項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="2fdbe-129">Visual Studio Code またはコマンド ラインを使用した Python</span><span class="sxs-lookup"><span data-stu-id="2fdbe-129">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="2fdbe-130">Python から新しい Q# プログラムを実行するには、次のコードを `host.py` として保存します。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-130">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    <span data-ttu-id="2fdbe-131">次に、コマンド ラインから Python ホスト プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-131">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="2fdbe-132">Visual Studio Code またはコマンド ラインを使用した C#</span><span class="sxs-lookup"><span data-stu-id="2fdbe-132">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="2fdbe-133">C# から新しい Q# プログラムを実行するには、次の C# コードを含めるように `Driver.cs` を変更します。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-133">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    <span data-ttu-id="2fdbe-134">次に、コマンド ラインから C# ホスト プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-134">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="2fdbe-135">Visual Studio 2019 を使用した C#</span><span class="sxs-lookup"><span data-stu-id="2fdbe-135">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="2fdbe-136">Visual Studio で C# から新しい Q# プログラムを実行するには、次の C# コードを含めるように `Driver.cs` を変更します。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-136">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    <span data-ttu-id="2fdbe-137">F5 キーを押すと、プログラムは実行を開始し、新しいポップアップ ウィンドウに次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-137">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    <span data-ttu-id="2fdbe-138">`ReflectAboutMarked` 操作は 4 回だけ呼び出され、Q# プログラムにより $2^{5} = 32$ の入力で "01010" の入力を見つけることができました。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-138">The `ReflectAboutMarked` operation is called only four times, but your Q# program was able to find the "01010" input amongst $2^{5} = 32$ possible inputs!</span></span>

## <a name="next-steps"></a><span data-ttu-id="2fdbe-139">次のステップ</span><span class="sxs-lookup"><span data-stu-id="2fdbe-139">Next steps</span></span>

<span data-ttu-id="2fdbe-140">クイックスタートをお読みいただきありがとうございます。Q# を使用して独自の量子アプリケーションを記述する方法の詳細について、次のリソースもご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="2fdbe-141">QDK 入門ガイドに戻る</span><span class="sxs-lookup"><span data-stu-id="2fdbe-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="2fdbe-142">より一般的なグローバーの検索アルゴリズムの[サンプル](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)を試す</span><span class="sxs-lookup"><span data-stu-id="2fdbe-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="2fdbe-143">グローバーの検索と Quantum Katas について学習する</span><span class="sxs-lookup"><span data-stu-id="2fdbe-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="2fdbe-144">グローバーの検索アルゴリズムの背後にある量子コンピューティング手法である[振幅増幅](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification)について読む</span><span class="sxs-lookup"><span data-stu-id="2fdbe-144">Read more about [Amplitude amplification](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="2fdbe-145">量子コンピューティングの概念</span><span class="sxs-lookup"><span data-stu-id="2fdbe-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="2fdbe-146">Quantum 開発キット サンプル</span><span class="sxs-lookup"><span data-stu-id="2fdbe-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
