---
title: Q# プログラミング言語と QDK とは
description: Microsoft Quantum 開発キットと Q# プログラミング言語について、および量子プログラムの作成方法について説明します。
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5db574b0380ffa1616cb3959d84925854df4e321
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863771"
---
# <a name="what-are-the-no-locq-programming-language-and-qdk"></a><span data-ttu-id="15837-103">Q# プログラミング言語と QDK とは</span><span class="sxs-lookup"><span data-stu-id="15837-103">What are the Q# programming language and QDK?</span></span>

<span data-ttu-id="15837-104">Q# は、量子アルゴリズムを開発および実行するための Microsoft のオープンソース プログラミング言語です。</span><span class="sxs-lookup"><span data-stu-id="15837-104">Q# is Microsoft’s open-source programming language for developing and running quantum algorithms.</span></span> <span data-ttu-id="15837-105">これは Quantum 開発キット (QDK) に含まれています。QDK には、[Q# ライブラリ](xref:microsoft.quantum.libraries)、[量子シミュレーター](xref:microsoft.quantum.machines)、[他のプログラミング環境用の拡張機能](xref:microsoft.quantum.install)、[API ドキュメント](xref:microsoft.quantum.standardlibsintro)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="15837-105">It’s part of the Quantum Development Kit (QDK), which includes [Q# libraries](xref:microsoft.quantum.libraries), [quantum simulators](xref:microsoft.quantum.machines), [extensions for other programming environments](xref:microsoft.quantum.install), and [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span> <span data-ttu-id="15837-106">QDK には、標準の Q# ライブラリに加えて、化学、機械学習、数値のライブラリも含まれています。</span><span class="sxs-lookup"><span data-stu-id="15837-106">In addition to the Standard Q# library, the QDK includes Chemistry, Machine Learning, and Numeric libraries.</span></span>

<span data-ttu-id="15837-107">プログラミング言語としての Q# では、Python、C#、F# から一般的な要素を取り入れ、ループ、if/then ステートメント、共通データ型を使用してプログラムを作成するための基本的な手続き型のモデルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="15837-107">As a programming language, Q# draws familiar elements from Python, C#, and F# and supports a basic procedural model for writing programs with loops, if/then statements, and common data types.</span></span> <span data-ttu-id="15837-108">また、新しい量子固有のデータ構造と演算も導入されています。</span><span class="sxs-lookup"><span data-stu-id="15837-108">It also introduces new quantum-specific data structures and operations.</span></span>

## <a name="what-can-i-do-with-the-qdk"></a><span data-ttu-id="15837-109">QDK でできること</span><span class="sxs-lookup"><span data-stu-id="15837-109">What can I do with the QDK?</span></span>

<span data-ttu-id="15837-110">QDK は Q# 用のフル機能の開発キットであり、さまざまな環境で実行できる量子アプリケーションを開発するために、一般的なツールと言語で使用できます。</span><span class="sxs-lookup"><span data-stu-id="15837-110">The QDK is a full-featured development kit for Q# that you can use with common tools and languages to develop quantum applications that you can run in various environments.</span></span> <span data-ttu-id="15837-111">Q# プログラムは、コンソール アプリケーションとして Jupyter Notebook 経由で実行するか、または Python または .NET ホスト プログラムを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="15837-111">Q# programs can run as a console application, through Jupyter Notebooks, or use a Python or .NET host program.</span></span>

### <a name="develop-in-common-tools-and-environments"></a><span data-ttu-id="15837-112">一般的なツールと環境で開発する</span><span class="sxs-lookup"><span data-stu-id="15837-112">Develop in common tools and environments</span></span>

<span data-ttu-id="15837-113">量子開発を [Visual Studio、Visual Studio Code](xref:microsoft.quantum.install.standalone)、[Jupyter Notebook](xref:microsoft.quantum.install.jupyter) と統合します。</span><span class="sxs-lookup"><span data-stu-id="15837-113">Integrate your quantum development with [Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone), and [Jupyter Notebooks](xref:microsoft.quantum.install.jupyter).</span></span> <span data-ttu-id="15837-114">組み込みの API を使用して、プログラムを、ホスト言語である [Python](xref:microsoft.quantum.install.python) および [.NET](xref:microsoft.quantum.install.cs) と組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="15837-114">Use the built-in APIs for pairing your programs with [Python](xref:microsoft.quantum.install.python) and [.NET](xref:microsoft.quantum.install.cs) host languages.</span></span>

### <a name="try-quantum-operations-and-domain-specific-libraries"></a><span data-ttu-id="15837-115">量子演算と分野固有のライブラリを試す</span><span class="sxs-lookup"><span data-stu-id="15837-115">Try quantum operations and domain-specific libraries</span></span>

<span data-ttu-id="15837-116">重ね合わせ、もつれ、およびその他の量子演算を確認するために、量子アルゴリズムを記述してテストします。</span><span class="sxs-lookup"><span data-stu-id="15837-116">Write and test quantum algorithms to explore superposition, entanglement, and other quantum operations.</span></span> <span data-ttu-id="15837-117">Q# ライブラリを使用すると、低レベルの演算シーケンスを設計しなくても、複雑な量子演算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="15837-117">The Q# libraries enable you to run complex quantum operations without having to design low-level operation sequences.</span></span>

### <a name="run-programs-in-simulators"></a><span data-ttu-id="15837-118">シミュレーターでプログラムを実行する</span><span class="sxs-lookup"><span data-stu-id="15837-118">Run programs in simulators</span></span>

<span data-ttu-id="15837-119">全状態の量子シミュレーターや限定された範囲の Toffoli シミュレーターで量子プログラムを実行するか、さまざまなリソース エスティメーターで Q# コードをテストします。</span><span class="sxs-lookup"><span data-stu-id="15837-119">Run your quantum programs on a full-state quantum simulator, a limited-scope Toffoli simulator, or test your Q# code in different resource estimators.</span></span> 

## <a name="where-can-i-learn-more"></a><span data-ttu-id="15837-120">詳細情報を得るには?</span><span class="sxs-lookup"><span data-stu-id="15837-120">Where can I learn more?</span></span>

|||
| ---- | ---- |
| <span data-ttu-id="15837-121">**量子コンピューティングが初めての場合**</span><span class="sxs-lookup"><span data-stu-id="15837-121">**I'm new to quantum computing**</span></span> | <span data-ttu-id="15837-122">[主要な概念](xref:microsoft.quantum.overview.understanding)に関するページで、量子物理学と量子コンピューティングの基礎を確認します。</span><span class="sxs-lookup"><span data-stu-id="15837-122">Review some basics of quantum physics and quantum computing in [Key Concepts](xref:microsoft.quantum.overview.understanding).</span></span>|
| <span data-ttu-id="15837-123">**Q# 言語について深く理解したい場合**</span><span class="sxs-lookup"><span data-stu-id="15837-123">**I want to dive deeper into the Q# language**</span></span> | <span data-ttu-id="15837-124">「[Q# ユーザー ガイド](xref:microsoft.quantum.guide)」で型、式、変数、量子プログラムの構造について確認します。</span><span class="sxs-lookup"><span data-stu-id="15837-124">Explore types, expressions, variables, and quantum program structure in the [Q# User Guide](xref:microsoft.quantum.guide).</span></span>|
| <span data-ttu-id="15837-125">**量子プログラムの作成を始めたい場合**</span><span class="sxs-lookup"><span data-stu-id="15837-125">**I just want to start writing quantum programs**</span></span> | <span data-ttu-id="15837-126">[クイックスタート](xref:microsoft.quantum.install)で、Q# 環境を設定し、量子プログラムの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="15837-126">Set up your Q# environment and start writing quantum programs in [QuickStarts](xref:microsoft.quantum.install).</span></span>|

## <a name="how-does-no-locq-work"></a><span data-ttu-id="15837-127">Q# のしくみ</span><span class="sxs-lookup"><span data-stu-id="15837-127">How does Q# work?</span></span>

<span data-ttu-id="15837-128">Q# プログラムは、スタンドアロン アプリケーションとしてコンパイルすることも、Python または .NET 言語で記述されたホスト プログラムによって呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="15837-128">A Q# program can compile into a standalone application or be called by a host program that is written either in Python or a .NET language.</span></span>

<span data-ttu-id="15837-129">プログラムをコンパイルして実行すると、量子シミュレーターのインスタンスが作成され、それに Q# コードが渡されます。</span><span class="sxs-lookup"><span data-stu-id="15837-129">When you compile and run the program, it creates an instance of the quantum simulator and passes the Q# code to it.</span></span> <span data-ttu-id="15837-130">シミュレーターでは、Q# コードを使用して量子ビット (量子粒子のシミュレーション) を作成し、変換を適用してその状態を変更します。</span><span class="sxs-lookup"><span data-stu-id="15837-130">The simulator uses the Q# code to create qubits (simulations of quantum particles) and apply transformations to modify their state.</span></span> <span data-ttu-id="15837-131">その後、シミュレーター内の量子演算の結果がプログラムに返されます。</span><span class="sxs-lookup"><span data-stu-id="15837-131">The results of the quantum operations in the simulator are then returned to the program.</span></span>  

<span data-ttu-id="15837-132">シミュレーター内で Q# コードを分離すると、アルゴリズムが量子物理学の法則に従うようになり、量子コンピューターで正しく実行できます。</span><span class="sxs-lookup"><span data-stu-id="15837-132">Isolating the Q# code in the simulator ensures that the algorithms follow the laws of quantum physics and can run correctly on quantum computers.</span></span>

![qsharp-code-flow](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a><span data-ttu-id="15837-134">QDK の使用方法</span><span class="sxs-lookup"><span data-stu-id="15837-134">How do I use the QDK?</span></span>

<span data-ttu-id="15837-135">Q# コンパイラ、Q# ライブラリ、量子シミュレーターなど、Q# プログラムの作成と実行に必要なものはすべて、ローカル コンピューターからインストールして実行できます。</span><span class="sxs-lookup"><span data-stu-id="15837-135">Everything you need to write and run Q# programs, including the Q# compiler, the Q# libraries, and the quantum simulators, can be installed and run from your local computer.</span></span> <span data-ttu-id="15837-136">最終的には、実際の量子コンピューターで Q# プログラムをリモートで実行できるようになりますが、それまでは、QDK で提供される量子シミュレーターによって正確で信頼性の高い結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="15837-136">Eventually you will be able to run your Q# programs remotely on an actual quantum computer, but until then the quantum simulators provided with the QDK provide accurate and reliable results.</span></span>

- <span data-ttu-id="15837-137">[Q# アプリケーション](xref:microsoft.quantum.install.standalone) の開発は、作業を開始するための最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="15837-137">Developing [Q# applications](xref:microsoft.quantum.install.standalone) is the quickest way to get started.</span></span>

- <span data-ttu-id="15837-138">スタンドアロンの [Jupyter Notebook を IQ#](xref:microsoft.quantum.install.jupyter) (Q# プログラムをコンパイル、シミュレート、視覚化するための Jupyter の拡張機能) で実行します。</span><span class="sxs-lookup"><span data-stu-id="15837-138">Run standalone [Jupyter Notebooks with IQ#](xref:microsoft.quantum.install.jupyter), a Jupyter extension for compiling, simulating, and visualizing Q# programs.</span></span>

- <span data-ttu-id="15837-139">[Python](xref:microsoft.quantum.install.python) を使い慣れている場合は、開始時にこれをホスト プログラミング プラットフォームとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="15837-139">If you are familiar with [Python](xref:microsoft.quantum.install.python), you can use it as a host programming platform to get started.</span></span> <span data-ttu-id="15837-140">Python は、開発者の間だけでなく、科学者、研究者、教師にも広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="15837-140">Python enjoys widespread use not only among developers, but also scientists, researchers and teachers.</span></span>

- <span data-ttu-id="15837-141">すでに [C#、F#、または VB.NET](xref:microsoft.quantum.install.cs) の使用経験があり、Visua Studio の開発環境に慣れている場合は、Q# への対応準備のために Visual Studio に追加する必要がある拡張機能はわずかです。</span><span class="sxs-lookup"><span data-stu-id="15837-141">If you already have experience with [C#, F#, or VB.NET](xref:microsoft.quantum.install.cs) and are familiar with the Visual Studio development environment, there are just a few extensions you need to add to Visual Studio to prepare it for Q#.</span></span>  

## <a name="summary"></a><span data-ttu-id="15837-142">まとめ</span><span class="sxs-lookup"><span data-stu-id="15837-142">Summary</span></span>

<span data-ttu-id="15837-143">Q# は、量子プログラムを開発するためのオープンソースのプログラミング言語です。</span><span class="sxs-lookup"><span data-stu-id="15837-143">Q# is an open-source programming language for developing quantum programs.</span></span> <span data-ttu-id="15837-144">これは、複雑な量子演算を作成できるようにするライブラリと、プログラムを正確に実行してテストするための量子シミュレーターを備えています。</span><span class="sxs-lookup"><span data-stu-id="15837-144">It has libraries that let you create complex quantum operations, and quantum simulators to accurately run and test your programs.</span></span> <span data-ttu-id="15837-145">Q# プログラムは、スタンドアロン アプリとして実行することも、Python または .NET のホスト プログラムから呼び出すこともでき、ローカル コンピューターから作成、実行、およびテストできます。</span><span class="sxs-lookup"><span data-stu-id="15837-145">Q# programs can run as standalone apps or be called from a Python or .NET host program, and can be written, run, and tested from your local computer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="15837-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="15837-146">Next Steps</span></span>

[<span data-ttu-id="15837-147">量子コンピューティングの線形代数</span><span class="sxs-lookup"><span data-stu-id="15837-147">Linear algebra for quantum computing</span></span>](xref:microsoft.quantum.overview.algebra)
