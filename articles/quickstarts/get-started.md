---
uid: microsoft.quantum.welcome
title: Quantum Development Kit (QDK) の概要
description: Microsoft Quantum 開発キットを使用して Q# で量子プロジェクトのプログラミングを開始する方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 9/29/2020
ms.topic: quickstart
no-loc:
- Q#
- $$v
ms.openlocfilehash: 62910becb5b3c7415ac575217230b6c8be55fd7e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858856"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a><span data-ttu-id="b21e6-103">Quantum Development Kit (QDK) の概要</span><span class="sxs-lookup"><span data-stu-id="b21e6-103">Get started with the Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="b21e6-104">Microsoft Quantum Development Kit にようこそ。</span><span class="sxs-lookup"><span data-stu-id="b21e6-104">Welcome to the Microsoft Quantum Development Kit!</span></span>  

<span data-ttu-id="b21e6-105">Quantum 開発キット (QDK) には、量子アプリケーション開発専用に設計されたプログラミング言語である Q# を使用して、独自の量子プログラムおよび実験を構築するために必要なあらゆるツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b21e6-105">The Quantum Development Kit (QDK) contains all the tools you'll need to build your own quantum programs and experiments with Q#, a programming language designed specifically for quantum application development.</span></span>

<span data-ttu-id="b21e6-106">すぐに始めるには、まず [QDK 設定ガイド](xref:microsoft.quantum.install)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b21e6-106">To jump right in, start with the [QDK set up guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="b21e6-107">Windows、Linux、または MacOS を搭載したマシンに Quantum 開発キットを設定して、独自の量子プログラムを作成するための手順が示されます。</span><span class="sxs-lookup"><span data-stu-id="b21e6-107">You'll be guided through setting up the Quantum Development Kit on Windows, Linux, or MacOS machines so that you can write your own quantum programs.</span></span>

<span data-ttu-id="b21e6-108">量子コンピューティングを初めて利用する場合は、「[概要](xref:microsoft.quantum.overview.introduction)」セクションを参照して、量子コンピューターで何が実行できのか、および量子コンピューティングの基礎を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b21e6-108">If you're new to quantum computing, review the [Overview](xref:microsoft.quantum.overview.introduction) section to learn what quantum computers can do and the fundamentals of quantum computing.</span></span>

## <a name="get-started-programming"></a><span data-ttu-id="b21e6-109">プログラミングを開始する</span><span class="sxs-lookup"><span data-stu-id="b21e6-109">Get started programming</span></span>

<span data-ttu-id="b21e6-110">Quantum 開発キットには、Q# を使用して量子プログラムを開発する方法を学習するためのさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="b21e6-110">The Quantum Development Kit provides many ways to learn how to develop a quantum program with Q#.</span></span>
<span data-ttu-id="b21e6-111">量子の力の利用を開始する場合は、チュートリアルを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="b21e6-111">To get up and running with the power of quantum, you can try out our tutorials:</span></span>

* <span data-ttu-id="b21e6-112">[量子乱数ジェネレーター](xref:microsoft.quantum.quickstarts.qrng) - "Q# Hello World" スタイルのアプリケーションであり、量子の概念を簡単に紹介し、量子アプリケーションを数分でビルドして実行できます。</span><span class="sxs-lookup"><span data-stu-id="b21e6-112">[Quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) - Start with a "Q# Hello World" style application, providing a brief introduction to quantum concepts while letting you build and run a quantum application in minutes.</span></span>
* <span data-ttu-id="b21e6-113">[Q# でのもつれの確認](xref:microsoft.quantum.write-program) - このチュートリアルでは、量子プログラミングの基本的な概念を示す Q# プログラムの記述方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b21e6-113">[Explore entanglement with Q#](xref:microsoft.quantum.write-program) - This tutorial guides you on writing a Q# program that demonstrates some of the foundational concepts of quantum programming.</span></span> <span data-ttu-id="b21e6-114">コーディングを開始する準備ができていない場合でも、QDK をインストールせずに説明を読み進めることで、Q# プログラミング言語の概要と量子コンピューティングの最初の概念を理解することができます。</span><span class="sxs-lookup"><span data-stu-id="b21e6-114">If you are not ready to start coding, you can still follow along without installing the QDK and get an overview of the Q# programming language and the first concepts of quantum computing.</span></span>
* <span data-ttu-id="b21e6-115">[グローバーの検索アルゴリズム](xref:microsoft.quantum.quickstarts.search) - この Q# プログラムの例では、低レベルの量子演算を抽象化する方法を探ることで、量子アルゴリズムを表すための Q# の能力を確認します。</span><span class="sxs-lookup"><span data-stu-id="b21e6-115">[Grover’s search algorithm](xref:microsoft.quantum.quickstarts.search) - Explore this example of a Q# program to get an idea of the power of Q# for expressing the quantum algorithm in a way that abstracts the low-level quantum operations.</span></span> <span data-ttu-id="b21e6-116">このチュートリアルでは、Visual Studio または Visual Studio Code を使用して、Q# アプリケーションとしてプログラムを開発する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b21e6-116">This tutorial guides you through developing the program as a Q# application, using Visual Studio or Visual Studio Code.</span></span>

## <a name="learning-further"></a><span data-ttu-id="b21e6-117">今後の学習</span><span class="sxs-lookup"><span data-stu-id="b21e6-117">Learning further</span></span>
* <span data-ttu-id="b21e6-118">Microsoft Learn では、量子コンピューティングの無料オンライン トレーニングを提供しています。</span><span class="sxs-lookup"><span data-stu-id="b21e6-118">Microsoft Learn offers free online training for quantum computing.</span></span> <span data-ttu-id="b21e6-119">[量子コンピューティングの基礎](https://docs.microsoft.com/learn/paths/quantum-computing-fundamentals/)ラーニング パスでは、量子コンピューティングと量子アルゴリズムの基本的な概念が紹介されており、Q# を使用して量子プログラムの構築を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="b21e6-119">The [Quantum computing foundations](https://docs.microsoft.com/learn/paths/quantum-computing-fundamentals/) Learning Path introduces the fundamental concepts of quantum computing and quantum algorithms, and gets you started building quantum programs using Q#.</span></span>
* <span data-ttu-id="b21e6-120">Q# プログラミングの詳細については、[Quantum Katas](https://github.com/Microsoft/QuantumKatas) に関する説明をご覧ください。これは、Q# のプログラミング演習を通じて量子コンピューティングを紹介する、マイペースで進められるプログラミング演習のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="b21e6-120">If you want to dive deeper into Q# programming, check out the [Quantum Katas](https://github.com/Microsoft/QuantumKatas) - a collection of self-paced programming exercises that introduce you to quantum computing via programming exercises in Q#.</span></span> <span data-ttu-id="b21e6-121">これらの katas の多くは、Q# ノートブックとしても利用できます。</span><span class="sxs-lookup"><span data-stu-id="b21e6-121">Many of these katas are also available as Q# Notebooks.</span></span> 
* <span data-ttu-id="b21e6-122">[サンプル リポジトリ](https://github.com/Microsoft/Quantum)では、Q# を使用して量子プログラムを作成する方法について複数の例を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="b21e6-122">Our [samples repository](https://github.com/Microsoft/Quantum) showcases multiple examples on how to write quantum programs using Q#.</span></span> <span data-ttu-id="b21e6-123">これらのサンプルのほとんどは、オープンソースの[量子ライブラリ](https://github.com/Microsoft/QuantumLibraries)を使用して記述されています。これには、[標準](xref:microsoft.quantum.libraries.standard.intro)および[化学](xref:microsoft.quantum.chemistry.concepts.intro)ライブラリ (以下の詳細を参照) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b21e6-123">Most of these samples are written using our open-source [quantum libraries](https://github.com/Microsoft/QuantumLibraries), including our [standard](xref:microsoft.quantum.libraries.standard.intro) and [chemistry](xref:microsoft.quantum.chemistry.concepts.intro) libraries (more info on these below).</span></span>

## <a name="key-concepts-for-quantum-computing"></a><span data-ttu-id="b21e6-124">量子コンピューティングの主要な概念</span><span class="sxs-lookup"><span data-stu-id="b21e6-124">Key concepts for quantum computing</span></span>

<span data-ttu-id="b21e6-125">量子開発の初心者の場合、これは少し面倒であると感じるかと思います。</span><span class="sxs-lookup"><span data-stu-id="b21e6-125">If you are a newcomer to quantum development, we know that this can all seem a bit daunting.</span></span> <span data-ttu-id="b21e6-126">これらの主要な概念を参照することで、量子の世界に足を踏み入れる手助けとなり、量子コンピューティングが従来のコンピューティングとどのように違うかを理解できます。</span><span class="sxs-lookup"><span data-stu-id="b21e6-126">These key concepts are designed to help you step into the quantum world and understand how quantum computing differs from classical computing.</span></span>

* [<span data-ttu-id="b21e6-127">量子コンピューティングについて</span><span class="sxs-lookup"><span data-stu-id="b21e6-127">Understanding quantum computing</span></span>](xref:microsoft.quantum.overview.understanding)
* [<span data-ttu-id="b21e6-128">量子コンピューターと量子シミュレーター</span><span class="sxs-lookup"><span data-stu-id="b21e6-128">Quantum computers and quantum simulators</span></span>](xref:microsoft.quantum.overview.simulators)
* [<span data-ttu-id="b21e6-129">Q# プログラミング言語と QDK とは</span><span class="sxs-lookup"><span data-stu-id="b21e6-129">What are the Q# programming language and the QDK?</span></span>](xref:microsoft.quantum.overview.q-sharp)
* [<span data-ttu-id="b21e6-130">量子コンピューティングの線形代数</span><span class="sxs-lookup"><span data-stu-id="b21e6-130">Linear algebra for quantum computing</span></span>](xref:microsoft.quantum.overview.algebra)

## <a name="quantum-development-kit-documentation"></a><span data-ttu-id="b21e6-131">Quantum Development Kit のドキュメント</span><span class="sxs-lookup"><span data-stu-id="b21e6-131">Quantum Development Kit Documentation</span></span>

<span data-ttu-id="b21e6-132">現在のドキュメントには、次の追加のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b21e6-132">The current documentation includes the following additional topics.</span></span>

### <a name="no-locq-developer-guides"></a><span data-ttu-id="b21e6-133">Q# 開発者ガイド</span><span class="sxs-lookup"><span data-stu-id="b21e6-133">Q# developer guides</span></span>

* <span data-ttu-id="b21e6-134">「[Q# ユーザー ガイド](xref:microsoft.quantum.guide)」では、Q# で量子プログラムを作成するための中核概念について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="b21e6-134">[Q# User Guide](xref:microsoft.quantum.guide) details the core concepts used to create quantum programs in Q#.</span></span>
* <span data-ttu-id="b21e6-135">[量子シミュレーターとホスト アプリケーション](xref:microsoft.quantum.machines)では、量子アルゴリズムがどのように実行されるか、どの量子コンピューターを使用できるか、および量子プログラム用に Q# 以外のドライバーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b21e6-135">[Quantum simulators and host applications](xref:microsoft.quantum.machines) describes how quantum algorithms are run, what quantum machines are available, and how to write a non-Q# driver for the quantum program.</span></span>

### <a name="no-locq-libraries"></a><span data-ttu-id="b21e6-136">Q# ライブラリ</span><span class="sxs-lookup"><span data-stu-id="b21e6-136">Q# libraries</span></span>

* <span data-ttu-id="b21e6-137">[Q# 標準ライブラリ](xref:microsoft.quantum.libraries.standard.intro)では、従来の言語制御の要件と Q# 量子アルゴリズムの両方をサポートする操作と関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="b21e6-137">[Q# standard libraries](xref:microsoft.quantum.libraries.standard.intro) describes the operations and functions that support both the classical language control requirement and the Q# quantum algorithms.</span></span> 
    <span data-ttu-id="b21e6-138">トピックには、制御フロー、データ構造、エラー修正、テスト、デバッグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b21e6-138">Topics include control flow, data structures, error correction, testing, and debugging.</span></span> 
* <span data-ttu-id="b21e6-139">[Q# 化学ライブラリ](xref:microsoft.quantum.chemistry.concepts.intro)では、量子化学シミュレーションをサポートする操作や関数について説明します。これは、量子コンピューティングの重要な応用です。</span><span class="sxs-lookup"><span data-stu-id="b21e6-139">[Q# chemistry library](xref:microsoft.quantum.chemistry.concepts.intro) describes the operations and functions that support quantum chemistry simulation---a critical application of quantum computing.</span></span> <span data-ttu-id="b21e6-140">トピックには、ハミルトン力学や量子位相推定のシミュレーションなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b21e6-140">Topics include simulating Hamiltonian dynamics and quantum phase estimation, among others.</span></span>
* <span data-ttu-id="b21e6-141">[Q# 数値ライブラリ](xref:microsoft.quantum.numerics.intro)では、対象のコンピューターのネイティブ操作に関して複雑な算術関数の表現をサポートする操作と関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="b21e6-141">[Q# numerics library](xref:microsoft.quantum.numerics.intro) describes the operations and functions that support expressing complicated arithmetic functions in terms of the native operations of target machines.</span></span>
* <span data-ttu-id="b21e6-142">[Q# ライブラリ リファレンス](xref:microsoft.quantum.apiref-intro)には、名前空間別のライブラリ エンティティに関する参照情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b21e6-142">[Q# library reference](xref:microsoft.quantum.apiref-intro) contains reference information about library entities by namespace.</span></span>

### <a name="general-quantum-computing"></a><span data-ttu-id="b21e6-143">一般的な量子コンピューティング</span><span class="sxs-lookup"><span data-stu-id="b21e6-143">General quantum computing</span></span>

* <span data-ttu-id="b21e6-144">[量子コンピューティングの概念](xref:microsoft.quantum.concepts.intro)では、量子コンピューティングへの線形代数の関連性、量子ビットの性質や使用法、量子回線の読み取り方法などのトピックを紹介します。</span><span class="sxs-lookup"><span data-stu-id="b21e6-144">[Quantum computing concepts](xref:microsoft.quantum.concepts.intro) includes topics such as the relevance of linear algebra to quantum computing, the nature and use of a qubit, how to read a quantum circuit, and more.</span></span>
* <span data-ttu-id="b21e6-145">[量子コンピューティング用語集](xref:microsoft.quantum.glossary)では、量子コンピューティングおよびプログラム開発に固有の重要な一部の用語を示します。</span><span class="sxs-lookup"><span data-stu-id="b21e6-145">[Quantum computing glossary](xref:microsoft.quantum.glossary) is a glossary of some crucial terms specific to quantum computing and program development.</span></span>
    <span data-ttu-id="b21e6-146">フィールドに慣れないお客様の場合、このドキュメントが手軽な参考資料として役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b21e6-146">If you are new to the field, this could be a handy reference as you read through our documentation.</span></span>
* <span data-ttu-id="b21e6-147">[関連項目](xref:microsoft.quantum.more-information)には、量子コンピューティングのトピックを詳しく解説する厳選された参考資料が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b21e6-147">[Further reading](xref:microsoft.quantum.more-information) contains specially selected references for in-depth coverage of quantum computing topics.</span></span>

### <a name="additional-info"></a><span data-ttu-id="b21e6-148">追加情報</span><span class="sxs-lookup"><span data-stu-id="b21e6-148">Additional info</span></span>

* <span data-ttu-id="b21e6-149">[Microsoft Quantum Development Kit のリリース ノート](xref:microsoft.quantum.relnotes)</span><span class="sxs-lookup"><span data-stu-id="b21e6-149">[Microsoft Quantum Development kit release notes](xref:microsoft.quantum.relnotes).</span></span>


## <a name="be-a-part-of-the-no-locq-open-source-community"></a><span data-ttu-id="b21e6-150">Q# のオープンソース コミュニティに参加する</span><span class="sxs-lookup"><span data-stu-id="b21e6-150">Be a part of the Q# Open-Source Community</span></span>

<span data-ttu-id="b21e6-151">オープンソースの開発キットである Quantum 開発キットにより、開発者はすべての人の量子コンピューティングへのアクセスを容易にすることができるため、世界で最も切迫している課題の一部を解決できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b21e6-151">The Quantum Development Kit is an open-source development kit that empowers developers to make quantum computing more accessible to all so that we can solve some of the world's most pressing challenges.</span></span>  <span data-ttu-id="b21e6-152">オープンソース ソフトウェアを必要とする教育機関は、その量子の学習と開発のために Q# をデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="b21e6-152">Academic institutions who require open-source software will be able to deploy Q# for their quantum learning and development.</span></span> <span data-ttu-id="b21e6-153">また、開発キットのオープンソース化により、開発者やドメインの専門家は、コードを使用して改善やアイデアを投稿する機会を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="b21e6-153">Open-sourcing the development kit also empowers developers and domain experts an opportunity to contribute improvements and ideas via their code.</span></span>

<span data-ttu-id="b21e6-154">お客様のフィードバック、参加、および Quantum 開発キットへの貢献が重要です。</span><span class="sxs-lookup"><span data-stu-id="b21e6-154">Your feedback, participation and contributions to the Quantum Development Kit is important.</span></span>  <span data-ttu-id="b21e6-155">Quantum Development Kit ソースの詳細のほか、フィードバックの提供方法、決定に参加する方法、この増加している量子開発プラットフォームに貢献する方法については、「[Quantum Development Kit に貢献する](xref:microsoft.quantum.contributing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b21e6-155">To learn more about the Quantum Development Kit sources, provide feedback, and find out how you can participate in the decisions and contribute to this growing quantum development platform, see [Contributing to the Quantum Development Kit](xref:microsoft.quantum.contributing).</span></span>

<span data-ttu-id="b21e6-156">Microsoft の量子コンピューティング イニシアチブに関する一般情報が必要な場合は、[Microsoft クォンタム](https://www.microsoft.com/en-us/quantum/)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b21e6-156">If you'd like more general information about Microsoft's quantum computing initiative, see [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).</span></span>
