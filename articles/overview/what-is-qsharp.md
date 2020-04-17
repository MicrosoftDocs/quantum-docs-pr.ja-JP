---
title: Q# および QDK とは
description: Microsoft によって作成された、量子コンピューター用のアプリケーションを開発するためのプログラミング言語であり、Microsoft の Quantum 開発キットの主要なコンポーネントである Q# について説明します
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "77907003"
---
# <a name="what-are-q-and-the-qdk"></a><span data-ttu-id="67fe3-103">Q# および QDK とは</span><span class="sxs-lookup"><span data-stu-id="67fe3-103">What are Q# and the QDK?</span></span>

<span data-ttu-id="67fe3-104">Q # は、量子コンピューティング専用に設計された機能を持つプログラミング言語です。</span><span class="sxs-lookup"><span data-stu-id="67fe3-104">Q# is a programming language with features specifically designed for use with quantum computing.</span></span>
<span data-ttu-id="67fe3-105">Microsoft の Quantum 開発キット (QDK) の主要なコンポーネントとして、ゲート シーケンスの最適化や量子コンピューターの物理的な実装などの技術的な詳細を気にすることなく、アルゴリズムにフォーカスできるフレームワークを量子プログラマーに提供します。</span><span class="sxs-lookup"><span data-stu-id="67fe3-105">As a key component of Microsoft's Quantum Development Kit (QDK), it provides quantum programmers a framework that allows you to focus on the algorithms without having to worry about technical details like gate sequence optimization or the physical implementation of a quantum computer.</span></span>

<span data-ttu-id="67fe3-106">QDK は、開発者が量子プログラムの作成を開始するのに必要なあらゆる機能を提供する幅広いツールで構成されています。</span><span class="sxs-lookup"><span data-stu-id="67fe3-106">The QDK comprises a wide range of tools which give developers everything they need to start writing quantum programs.</span></span>
<span data-ttu-id="67fe3-107">QDK には、Q# 言語と共に次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-107">Alongside the Q# language, the QDK includes:</span></span>
* <span data-ttu-id="67fe3-108">*Q # ライブラリ*。これにより、開発者は実際の量子アプリケーションをすぐに作成できます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-108">the *Q# libraries*, which allow developers to hit the ground running and create real-world quantum applications today</span></span>
* <span data-ttu-id="67fe3-109">Q# プログラムを実行できるさまざまな "*ターゲット マシン*"。</span><span class="sxs-lookup"><span data-stu-id="67fe3-109">various *target machines* on which Q# programs can be run.</span></span> <span data-ttu-id="67fe3-110">これには、大規模な量子プログラム用のリソースのエスティメーターとシミュレーター、およびノイズフリーの量子コンピューターとして動作する完全状態の量子シミュレーターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-110">These include resource estimators and simulators for larger quantum programs, as well as a full-state quantum simulator, which behaves as a noise-free quantum computer.</span></span> <span data-ttu-id="67fe3-111">後者は、アイデアの考察、プログラムのデバッグ、および量子物理学の学習に非常に役立ちますが、比較的少ない量子ビットを持つプログラムに対してのみ効率的です。</span><span class="sxs-lookup"><span data-stu-id="67fe3-111">The latter is very useful for tinkering with ideas, debugging programs, and learning about quantum physics, but only efficient for programs with relatively few qubits.</span></span> <span data-ttu-id="67fe3-112">今後、ターゲット マシンとして量子コンピューティング ハードウェアが利用可能になることを期待しています。</span><span class="sxs-lookup"><span data-stu-id="67fe3-112">We're very much looking forward to making quantum computing hardware available as target machines in the future.</span></span>
* <span data-ttu-id="67fe3-113">Q# での作業を可能な限りシームレスにする "*ツール*" (Visual Studio と VS Code の拡張機能、Python や Jupyter Notebooks で使用するパッケージなど)。</span><span class="sxs-lookup"><span data-stu-id="67fe3-113">*tools* for making work with Q# as seamless as possible, such as extensions for Visual Studio and VS Code, and packages for use with Python and Jupyter Notebooks.</span></span>
* <span data-ttu-id="67fe3-114">Python や C# などの従来のホスト言語と Q # を連携させるための" *API ドキュメント*"</span><span class="sxs-lookup"><span data-stu-id="67fe3-114">*API documentation* for pairing Q# with classical host languages such as Python and C#</span></span>

<span data-ttu-id="67fe3-115">通常、Microsoft の Quantum 開発キットを使用して開発されたアプリケーションは、次の 2 つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-115">Applications developed with Microsoft's Quantum Development Kit typically consist of two parts:</span></span>
1. <span data-ttu-id="67fe3-116">1 つ以上の量子アルゴリズム。Q# 量子プログラミング言語を使用して実装され、従来のホスト プログラムによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-116">One or more quantum algorithms, implemented using the Q# quantum programming language, and invoked by the classical host program.</span></span> <span data-ttu-id="67fe3-117">これは、次のもので構成されます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-117">These consist of</span></span> 
    - <span data-ttu-id="67fe3-118">Q # 演算: 量子演算を含むサブルーチン</span><span class="sxs-lookup"><span data-stu-id="67fe3-118">Q# operations: subroutines containing quantum operations, and</span></span> 
    - <span data-ttu-id="67fe3-119">Q # 関数: 量子アルゴリズム内で使用される従来のサブルーチン。</span><span class="sxs-lookup"><span data-stu-id="67fe3-119">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="67fe3-120">従来のプログラム。Python や C# などの従来のプログラミング言語で実装されます。メイン エントリ ポイントとして機能し、量子アルゴリズムを実行する必要があるときに Q# 演算を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="67fe3-120">A classical program, implemented in a classical programming language like Python or C#, that serves as the main entry point and will invoke Q# operations when it wants to execute a quantum algorithm.</span></span>

## <a name="write-quantum-programs-not-quantum-circuits"></a><span data-ttu-id="67fe3-121">量子回路ではなく、量子プログラムを作成する</span><span class="sxs-lookup"><span data-stu-id="67fe3-121">Write quantum programs, not quantum circuits</span></span>

<span data-ttu-id="67fe3-122">初期の量子コンピューティングでは、アルゴリズムは、古典コンピューティングの回路図に似た図に視覚化されていました。</span><span class="sxs-lookup"><span data-stu-id="67fe3-122">In the early days of quantum computing algorithms were visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>
<span data-ttu-id="67fe3-123">回路モデルは長年の量子コンピューティングの研究において役に立っていますが、Microsoft では開発者が Q# を使用することで、量子回路を超えた量子アルゴリズムとアプリケーションを開発できると考えています。</span><span class="sxs-lookup"><span data-stu-id="67fe3-123">While the circuit model has been useful for many years in quantum computing research, here at Microsoft, we believe that developers can go beyond quantum circuits and develop quantum algorithms and applications using Q#.</span></span>
<span data-ttu-id="67fe3-124">Q# 言語は、長年にわたる従来のソフトウェア開発を通じて学んだことを活用するために構築されており、量子コンピューティング向けの高度な言語機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="67fe3-124">The Q# language was built to take advantage of what we’ve learned through decades of classical software development, and empower quantum developers with high-level language functionality targeted for quantum computing.</span></span>

## <a name="how-does-q-work"></a><span data-ttu-id="67fe3-125">Q# のしくみ</span><span class="sxs-lookup"><span data-stu-id="67fe3-125">How does Q# work?</span></span>

<span data-ttu-id="67fe3-126">Q# プログラミング言語には、アルゴリズムを開発するための直観的な型、操作、論理式のセットが用意されているため、量子コンピューターの内部ロジックについて心配する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="67fe3-126">The Q# programming language provides you with an intuitive set of types, operations, and logic expressions to develop algorithms without having to worry about the internal logic of the quantum computer.</span></span>

<span data-ttu-id="67fe3-127">Q# の基本的な構成要素の 1 つは `Qubit` 型で、実際の量子ビットと同じように、コピーすることも直接アクセスすることもできません。</span><span class="sxs-lookup"><span data-stu-id="67fe3-127">One of the fundamental building blocks of Q# is the `Qubit` type, which cannot be copied or directly accessed, just like a real qubit.</span></span>
<span data-ttu-id="67fe3-128">代わりに、これを測定し、測定の結果を `Result` 変数 (`Zero` と `One` の 2 つの値を取ることができる Q# 型) に格納することができます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-128">Instead, we can measure it and store the outcome of the measurement in a `Result` variable, a Q# type that can take two possible values: `Zero` and `One`.</span></span>
<span data-ttu-id="67fe3-129">このようなコンストラクトにより、アルゴリズムで量子の物理法則が常に尊重され、量子コンピューターやシミュレーターで正しく実行できます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-129">Constructs like this one guarantee that algorithms always respect the laws of quantum physics and can run correctly on quantum computers or simulators.</span></span>

<span data-ttu-id="67fe3-130">また、Q# には条件やループなど従来から使用されている細かいロジック機能もいくつか含まれており、すべての量子法則が尊重されるようになっています。</span><span class="sxs-lookup"><span data-stu-id="67fe3-130">Q# also includes classical logic features like conditionals and loops with some subtleties to make sure that all the quantum rules are being respected.</span></span>
<span data-ttu-id="67fe3-131">たとえば、決定論的な従来のサブルーチンのみを含む関数内で量子演算が呼び出されないようにするためにループが実行される方法を制約するなどです。</span><span class="sxs-lookup"><span data-stu-id="67fe3-131">For example, constraining the way loops are executed to ensure that quantum operations are not called within functions which may only contain deterministic classical subroutines.</span></span>

<span data-ttu-id="67fe3-132">Q# プログラムは、よく C# や Python で記述されたホスト プログラムと組み合わせて使用されます。これにより、従来から使用されているコードと量子コードを容易に編成できます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-132">Q# programs are often paired with a host program written in C# or Python, which can provide convenient organization of classical and quantum code.</span></span>
<span data-ttu-id="67fe3-133">QDK は、C# や Python などの言語をサポートするだけでなく、IQ# Jupyter カーネルを使用することで Jupyter Notebook のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="67fe3-133">In addition to supporting languages such as C# and Python, the QDK provides Jupyter Notebook support with the IQ# Jupyter kernel.</span></span>

## <a name="what-can-i-use-q-for"></a><span data-ttu-id="67fe3-134">Q# の用途</span><span class="sxs-lookup"><span data-stu-id="67fe3-134">What can I use Q# for?</span></span>

### <a name="use-q-to-learn-quantum-computing"></a><span data-ttu-id="67fe3-135">Q# を使用して量子コンピューティングを学習する</span><span class="sxs-lookup"><span data-stu-id="67fe3-135">Use Q# to learn quantum computing</span></span>

<span data-ttu-id="67fe3-136">従来、量子コンピューティングを学習するには、量子ゲートと量子測定の順序付けられたシーケンスの形式でアルゴリズムを理解するために、回路モデルを学習する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="67fe3-136">Until now, to learn quantum computing you needed to learn the circuit model to understand the algorithms in the form of ordered sequences of quantum gates and measurements.</span></span> <span data-ttu-id="67fe3-137">Q# では、別のパスを使用できます。量子プログラムを記述することで量子コンピューティングを学べます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-137">With Q# you can take another path: learn quantum computing by writing quantum programs.</span></span>

### <a name="use-q-to-design-quantum-algorithms"></a><span data-ttu-id="67fe3-138">Q# を使用して量子アルゴリズムを設計する</span><span class="sxs-lookup"><span data-stu-id="67fe3-138">Use Q# to design quantum algorithms</span></span>

<span data-ttu-id="67fe3-139">Q# には、多くのライブラリとユーザー定義型が用意されており、ツールの実装や高度な量子アルゴリズムの構築に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-139">Q# provides you with an increasing number of libraries and user-defined types that will help you to implement tools and build advanced quantum algorithms.</span></span> <span data-ttu-id="67fe3-140">たとえば、q1 と q2 という 2 つの量子ビットを使用する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="67fe3-140">For example, you need to entangle two-qubits q1 and q2?</span></span> <span data-ttu-id="67fe3-141">量子ビットを使用するのに、必要なゲートを個別に適用するのではなく、既に組み込まれている操作 `PrepareEntangledState([q1], [q2])` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-141">Instead of applying individually the necessary gates to get the qubits entangled you can use the already built-in operation `PrepareEntangledState([q1], [q2])`.</span></span>

### <a name="use-q-to-estimate-quantum-resources"></a><span data-ttu-id="67fe3-142">Q# を使用して量子リソースを見積もる</span><span class="sxs-lookup"><span data-stu-id="67fe3-142">Use Q# to estimate quantum resources</span></span>

<span data-ttu-id="67fe3-143">Quantum Development Kit (QDK) に付属する完全状態の量子シミュレーターを使用し、Q# プログラムの実行をシミュレーションできます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-143">You can simulate the execution of your Q# program using the full state quantum simulator that is provided with the Quantum Development Kit (QDK).</span></span>  <span data-ttu-id="67fe3-144">QDK からは、リソースの見積もりツールも提供されます。このツールを利用すると、シミュレーターでは大きすぎて実行できない Q# プログラムの実行に関する分析情報が与えられます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-144">The QDK also provides resource estimators that give you insights on the performance of Q# programs that are too large to be run on a simulator.</span></span>  <span data-ttu-id="67fe3-145">これはアルゴリズム デザイナーにとって非常に貴重な情報です。以前の小規模な量子ハードウェアで実行するため、少ないリソースを使用するようにプログラムを調整できるからです (たとえば、実行されるキュービットの数が少なければ、演算の数も少なくなります)。</span><span class="sxs-lookup"><span data-stu-id="67fe3-145">This is highly valuable for algorithm designers, because they can tune their programs to use fewer resources (e.g. fewer number of qubits running for fewer numbers of operations), to run on earlier smaller scale quantum hardware.</span></span>

### <a name="use-q-to-validate-hardware-performance"></a><span data-ttu-id="67fe3-146">Q# を使用してハードウェアのパフォーマンスを検証する</span><span class="sxs-lookup"><span data-stu-id="67fe3-146">Use Q# to validate hardware performance</span></span>

<span data-ttu-id="67fe3-147">Q# の長所は、プログラムを 1 回記述すれば、デバッグのために量子シミュレーターで実行したり、さまざまな量子コンピューター ハードウェアで実行したりできることです。</span><span class="sxs-lookup"><span data-stu-id="67fe3-147">The beauty of Q# is that a program can be written once and run on quantum simulators for debugging, and run on different quantum computer hardware.</span></span>  <span data-ttu-id="67fe3-148">Q# で記述されたベンチマーク プログラムを実行し、ハードウェアのパフォーマンスを検証したり、量子コンピューターが進化し、新しい量子コンピューターが利用可能になったとき、結果を比較したりできます。</span><span class="sxs-lookup"><span data-stu-id="67fe3-148">Benchmark programs written in Q# can be run to validate hardware performance and compare results as quantum computers evolve and new quantum computers become available.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="67fe3-149">次のステップ</span><span class="sxs-lookup"><span data-stu-id="67fe3-149">Next steps</span></span>

* [<span data-ttu-id="67fe3-150">量子コンピューティングを学ぶ方法</span><span class="sxs-lookup"><span data-stu-id="67fe3-150">How do I learn about quantum computing?</span></span>](xref:microsoft.quantum.overview.learn)
* [<span data-ttu-id="67fe3-151">Microsoft Quantum 開発キットの概要</span><span class="sxs-lookup"><span data-stu-id="67fe3-151">Get started with the Microsoft Quantum Development Kit</span></span>](xref:microsoft.quantum.welcome)
