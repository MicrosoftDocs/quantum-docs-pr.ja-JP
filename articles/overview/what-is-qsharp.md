---
title: Q# とは
description: Microsoft によって作成された、量子コンピューター用のアプリケーションを開発するためのプログラミング言語である Q# について説明します。
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: e04228ff62092a15c529297bd56b9ee48399f4a5
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443955"
---
# <a name="what-is-q"></a><span data-ttu-id="a8fea-103">Q# とは</span><span class="sxs-lookup"><span data-stu-id="a8fea-103">What is Q#?</span></span>

<span data-ttu-id="a8fea-104">Q# は、量子コンピューティング用の特別な機能を備えたプログラミング言語です。</span><span class="sxs-lookup"><span data-stu-id="a8fea-104">Q# is a programming language with features that are special to quantum computing.</span></span> <span data-ttu-id="a8fea-105">Q# は、ゲート シーケンスの最適化や量子コンピューターの物理的な実装などの技術的な詳細を気にすることなく、アルゴリズムにフォーカスできるフレームワークを量子プログラマーに提供します。</span><span class="sxs-lookup"><span data-stu-id="a8fea-105">Q# provides quantum programmers a framework that allows you to focus on the algorithms without having to care about technical details like gate sequence optimization or the physical implementation of a quantum computer.</span></span>

<span data-ttu-id="a8fea-106">Q# プログラミング言語には、アルゴリズムを開発するための直観的な型、操作、論理式のセットが用意されているため、量子コンピューターの内部ロジックについて心配する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="a8fea-106">The Q# programming language provides you with an intuitive set of types, operations and logic expressions to develop algorithms without having to worry about the internal logic of the quantum computer.</span></span>

## <a name="code-algorithms"></a><span data-ttu-id="a8fea-107">コードのアルゴリズム</span><span class="sxs-lookup"><span data-stu-id="a8fea-107">Code algorithms</span></span>

<span data-ttu-id="a8fea-108">初期の量子コンピューティングでは、アルゴリズムは、古典コンピューティングの回路図に似た図に視覚化されていました。</span><span class="sxs-lookup"><span data-stu-id="a8fea-108">In the early days of quantum computing algorithms were visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>  <span data-ttu-id="a8fea-109">回路モデルは長年の量子コンピューティングの研究において非常に役に立っていますが、Microsoft では開発者が Q# を使用することで、量子回路を超えた量子アルゴリズムとアプリケーションを開発できると考えています。</span><span class="sxs-lookup"><span data-stu-id="a8fea-109">While the circuit model has been very useful for many years in quantum computing research, here at Microsoft, we believe that developers can go beyond quantum circuits and develop quantum algorithms and applications using Q#.</span></span> <span data-ttu-id="a8fea-110">Q# 言語は、長年にわたる従来のソフトウェア開発を通じて学んだことを活用するために構築されており、量子コンピューティングに特化した高度な言語機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a8fea-110">The Q# language was built to take advantage of what we’ve learned through decades of classical software development, and empower quantum developers with high-level language functionality specifically targeted for quantum computing.</span></span>


## <a name="how-does-q-work"></a><span data-ttu-id="a8fea-111">Q# のしくみ</span><span class="sxs-lookup"><span data-stu-id="a8fea-111">How does Q# work?</span></span>

<span data-ttu-id="a8fea-112">Q# の基本的な構成要素の 1 つは `Qubit` 型で、実際の量子ビットと同じように、コピーすることも直接アクセスすることもできません。</span><span class="sxs-lookup"><span data-stu-id="a8fea-112">One of the fundamental building blocks of Q# is the `Qubit` type, which cannot be copied or directly accessed, just like a real qubit.</span></span> <span data-ttu-id="a8fea-113">代わりに、これを測定し、測定の結果を `Result` 変数 (`Zero` と `One` の 2 つの値を取ることができる Q# 型) に格納することができます。</span><span class="sxs-lookup"><span data-stu-id="a8fea-113">Instead, we can measure it and store the outcome of the measurement in a `Result` variable, a Q# type that can take two possible values: `Zero` and `One`.</span></span> <span data-ttu-id="a8fea-114">このようなコンストラクトにより、アルゴリズムで量子の物理法則が常に尊重され、量子コンピューターやシミュレーターで正しく実行できます。</span><span class="sxs-lookup"><span data-stu-id="a8fea-114">Constructs like this one guarantee that algorithms always respect the laws of quantum physics and can run correctly on quantum computers or simulators.</span></span>

<span data-ttu-id="a8fea-115">また、Q# には条件やループなど従来から使用されている細かいロジック機能もいくつか含まれており、すべての量子法則が尊重されるようにします。</span><span class="sxs-lookup"><span data-stu-id="a8fea-115">Q# also includes classical logic features like conditionals or loops with some subtleties to make sure that all the quantum rules are being respected.</span></span> <span data-ttu-id="a8fea-116">たとえば、量子演算は元に戻すことができる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8fea-116">For example, quantum operations need to be reversible.</span></span> <span data-ttu-id="a8fea-117">これにより、ループの実行方法にいくつかの制約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a8fea-117">This enforces some constraints on the way loops are executed.</span></span>

<span data-ttu-id="a8fea-118">Q# プログラムは、よく C# や Python で記述されたホスト プログラムと組み合わせて使用されます。これにより、従来から使用されているコードと量子コードを容易に編成できます。</span><span class="sxs-lookup"><span data-stu-id="a8fea-118">Q# programs are often paired with a host program written in C# or Python, which can provide convenient organization of classical and quantum code.</span></span> <span data-ttu-id="a8fea-119">QDK は、C# や Python などの .NET 言語をサポートするだけでなく、IQ# Jupyter カーネルを使用することで Jupyter Notebook のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="a8fea-119">In addition to supporting .NET languages such as C# and Python, the QDK provides Jupyter Notebook support with the IQ# Jupyter kernel.</span></span>

## <a name="use-q-to-learn-quantum-computing"></a><span data-ttu-id="a8fea-120">Q# を使用して量子コンピューティングを学習する</span><span class="sxs-lookup"><span data-stu-id="a8fea-120">Use Q# to learn quantum computing</span></span>

<span data-ttu-id="a8fea-121">従来、量子コンピューティングを学習するには、量子ゲートと量子測定の順序付けられたシーケンスの形式でアルゴリズムを理解するために、回路モデルを学習する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="a8fea-121">Until now, to learn quantum computing you needed to learn the circuit model to understand the algorithms in the form of ordered sequences of quantum gates and measurements.</span></span> <span data-ttu-id="a8fea-122">Q# では、別のパスを使用できます。量子プログラムを記述することで量子コンピューティングを学べます。</span><span class="sxs-lookup"><span data-stu-id="a8fea-122">With Q# you can take another path: learn quantum computing by writing quantum programs.</span></span>

## <a name="use-q-to-design-quantum-algorithms"></a><span data-ttu-id="a8fea-123">Q# を使用して量子アルゴリズムを設計する</span><span class="sxs-lookup"><span data-stu-id="a8fea-123">Use Q# to design quantum algorithms</span></span>

<span data-ttu-id="a8fea-124">Q# には、多くのライブラリとユーザー定義型が用意されており、ツールの実装や高度な量子アルゴリズムの構築に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="a8fea-124">Q# provides you with an increasing number of libraries and user-defined types that will help you to implement tools and build advanced quantum algorithms.</span></span> <span data-ttu-id="a8fea-125">たとえば、q1 と q2 という 2 つの量子ビットを使用する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="a8fea-125">For example, you need to entangle two-qubits q1 and q2?</span></span> <span data-ttu-id="a8fea-126">量子ビットを使用するのに、必要なゲートを個別に適用するのではなく、既に組み込まれている操作 `PrepareEntangledState([q1], [q2])` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a8fea-126">Instead of applying individually the necessary gates to get the qubits entangled you can use the already built-in operation `PrepareEntangledState([q1], [q2])`.</span></span>

## <a name="use-q-to-estimate-quantum-resources"></a><span data-ttu-id="a8fea-127">Q# を使用して量子リソースを見積もる</span><span class="sxs-lookup"><span data-stu-id="a8fea-127">Use Q# to estimate quantum resources</span></span>

<span data-ttu-id="a8fea-128">Quantum Development Kit (QDK) に付属する完全状態の量子シミュレーターを使用し、Q# プログラムの実行をシミュレーションできます。</span><span class="sxs-lookup"><span data-stu-id="a8fea-128">You can simulate the execution of your Q# program using the full state quantum simulator that is provided with the Quantum Development Kit (QDK).</span></span>  <span data-ttu-id="a8fea-129">QDK からは、リソースの見積もりツールも提供されます。このツールを利用すると、シミュレーターでは大きすぎて実行できない Q# プログラムの実行に関する分析情報が与えられます。</span><span class="sxs-lookup"><span data-stu-id="a8fea-129">The QDK also provides resource estimators that give you insights on the performance of Q# programs that are too big to be run on a simulator.</span></span>  <span data-ttu-id="a8fea-130">これはアルゴリズム デザイナーにとって非常に貴重な情報です。以前の小規模な量子ハードウェアで実行するため、少ないリソースを使用するようにプログラムを調整できるからです (たとえば、実行されるキュービットの数が少なければ、演算の数も少なくなります)。</span><span class="sxs-lookup"><span data-stu-id="a8fea-130">This is highly valuable for algorithm designers, because they can tune their programs to use fewer resources (e.g. fewer number of qubits running for fewer numbers of operations), to run on earlier smaller scale quantum hardware.</span></span>   

## <a name="use-q-to-validate-hardware-performance"></a><span data-ttu-id="a8fea-131">Q# を使用してハードウェアのパフォーマンスを検証する</span><span class="sxs-lookup"><span data-stu-id="a8fea-131">Use Q# to validate hardware performance</span></span>

<span data-ttu-id="a8fea-132">Q# の長所は、プログラムを 1 回記述すれば、デバッグのために量子シミュレーターで実行したり、複数の量子コンピューター ハードウェアで実行したりできることです。</span><span class="sxs-lookup"><span data-stu-id="a8fea-132">The beauty of Q# is that a program can be written once and run on quantum simulators for debugging, and run on multiple quantum computer hardware.</span></span>  <span data-ttu-id="a8fea-133">Q# で記述されたベンチマーク プログラムを実行し、ハードウェアのパフォーマンスを検証したり、量子コンピューターが進化し、新しい量子コンピューターが利用可能になったとき、結果を比較したりできます。</span><span class="sxs-lookup"><span data-stu-id="a8fea-133">Benchmark programs written in Q# can be run to validate hardware performance and compare results as quantum computers evolve and new quantum computers become available.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="a8fea-134">次の手順</span><span class="sxs-lookup"><span data-stu-id="a8fea-134">Next steps</span></span>

* [<span data-ttu-id="a8fea-135">量子コンピューティングを学ぶ方法</span><span class="sxs-lookup"><span data-stu-id="a8fea-135">How do I learn quantum computing?</span></span>](xref:microsoft.quantum.overview.learn)
* [<span data-ttu-id="a8fea-136">Microsoft Quantum 開発キットの概要</span><span class="sxs-lookup"><span data-stu-id="a8fea-136">Get started with the Microsoft Quantum Development Kit</span></span>](xref:microsoft.quantum.welcome)
