---
title: Q# ユーザー ガイド
description: ユーザー ガイドの目的と内容の概要
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: 078d86c808b26c7f0b7b2577020cd9cef9491a9d
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885016"
---
# <a name="the-q-user-guide"></a><span data-ttu-id="7e879-103">Q# ユーザー ガイド</span><span class="sxs-lookup"><span data-stu-id="7e879-103">The Q# User Guide</span></span>

<span data-ttu-id="7e879-104">Q# ユーザー ガイドへようこそ。</span><span class="sxs-lookup"><span data-stu-id="7e879-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="7e879-105">このガイドの様々なトピックでは、Q# 言語の主要概念と、量子プログラムを記述するために必要なすべての情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e879-105">In the different topics of this guide, we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="7e879-106">ユーザー ガイドの内容</span><span class="sxs-lookup"><span data-stu-id="7e879-106">User Guide Contents</span></span>

- <span data-ttu-id="7e879-107">[Q# の基本](xref:microsoft.quantum.guide.basics):Q# プログラミング言語の目的と機能に関する概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e879-107">[Q# Basics](xref:microsoft.quantum.guide.basics): An introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

- <span data-ttu-id="7e879-108">[Q# プログラム実行する方法:](xref:microsoft.quantum.guide.host-programs) Q# プログラムの実行方法について説明します。また、コマンド ライン、Q# Jupyter Notebook、または Python や .NET 言語で記述された従来のホスト プログラムから、プログラムを呼び出すためのさまざまな方法の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="7e879-108">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is executed, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

### <a name="q-language"></a><span data-ttu-id="7e879-109">Q# 言語</span><span class="sxs-lookup"><span data-stu-id="7e879-109">Q# Language</span></span>

- <span data-ttu-id="7e879-110">[Q# の型](xref:microsoft.quantum.guide.types):Q# の型モデルを紹介し、型を指定して操作するための構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e879-110">[Types in Q#](xref:microsoft.quantum.guide.types): Lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="7e879-111">[型式](xref:microsoft.quantum.guide.expressions):Q# の各型の値の指定、参照、結合、および操作を行う方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="7e879-111">[Type Expressions](xref:microsoft.quantum.guide.expressions): Details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="7e879-112">Q# の使用</span><span class="sxs-lookup"><span data-stu-id="7e879-112">Using Q#</span></span>

- <span data-ttu-id="7e879-113">[Q# のファイル構造](xref:microsoft.quantum.guide.filestructure):`*.qs` Q# ファイルの構造と構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e879-113">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): Describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="7e879-114">[演算と関数](xref:microsoft.quantum.guide.operationsfunctions):Q# 言語の 2 つの呼び出し可能な型について詳しく説明します。すなわち、"*演算*" (量子ビット レジスタに対するアクションを含みます) と "*関数*" (従来の情報と厳密に連携して機能します) です。</span><span class="sxs-lookup"><span data-stu-id="7e879-114">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): Details the two callable types of the Q# language: *operations*, which include action on qubit registers, and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="7e879-115">ここでは、adjoint および制御されたバージョンの量子操作を含め、これらを定義して呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e879-115">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="7e879-116">[変数](xref:microsoft.quantum.guide.variables): Q# プログラム内における変数の役割と、それらを効果的に活用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e879-116">[Variables](xref:microsoft.quantum.guide.variables): Describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="7e879-117">たとえば、バインド スコープに関する情報に加えて、変更できない変数と変更可能な変数の違い、およびそれらを割り当てまたは再割り当てする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="7e879-117">For example, you can find information about binding scopes, as well as the difference between immutable and mutable variables and how to assign or re-assign them.</span></span>

- <span data-ttu-id="7e879-118">[量子ビットの操作](xref:microsoft.quantum.guide.qubits):個々の量子ビットと量子ビットの系を扱うために使用する Q# の機能について説明します。具体的には、それらの割り当て、それらに対する演算の実行、それらの測定です。</span><span class="sxs-lookup"><span data-stu-id="7e879-118">[Working with qubits](xref:microsoft.quantum.guide.qubits): Describes the features of Q# used to address individual qubits and systems of qubits, specifically, allocating them, performing operations on them, and measuring them.</span></span> 

- <span data-ttu-id="7e879-119">[制御フロー](xref:microsoft.quantum.guide.controlflow):Q# で使用できるプログラミング制御フロー パターンについて詳しく説明します。これには、多くの標準的な手法 (条件付き実行、for ループ、while ループなど) に加え、量子固有の "成功するまで繰り返す" パターンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e879-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): Details the programming control flow patterns available in Q#, which includes many standard techniques (such as conditional execution, for loops, while loops) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="7e879-120">[テストとデバッグ](xref:microsoft.quantum.guide.testingdebugging):自分のコードが想定どおりに動作していることを確かめるためのいくつかの手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e879-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="7e879-121">量子情報の一般的な不透明性により、量子プログラムのデバッグには特殊な手法が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e879-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="7e879-122">さいわい、Q# では、プログラマーが慣れている従来のデバッグ手法の多くと、量子特有の手法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7e879-122">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="7e879-123">これには、Q# での単体テストの作成や実行、コード内の値と確率に対する "*アサーション*" の埋め込み、ターゲット コンピューターの状態を出力する `Dump` 関数などが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7e879-123">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="7e879-124">その後者を完全状態シミュレーターと共に使用して、いくつかの量子限界を回避することで計算の特定の部分をデバッグすることができます (例: [量子複製不可能定理](xref:microsoft.quantum.concepts.pauli))。</span><span class="sxs-lookup"><span data-stu-id="7e879-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="7e879-125">量子シミュレーターとリソース エスティメーター</span><span class="sxs-lookup"><span data-stu-id="7e879-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="7e879-126">[量子シミュレーターとホスト アプリケーション](xref:microsoft.quantum.machines):使用可能なさまざまなシミュレーターの概要と、ホスト プログラムとターゲット コンピューター間の一般的な実行モデル。</span><span class="sxs-lookup"><span data-stu-id="7e879-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well as the general execution model between host programs and target machines.</span></span>

- <span data-ttu-id="7e879-127">[完全状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator):完全な量子状態をシミュレートするターゲット コンピューター。</span><span class="sxs-lookup"><span data-stu-id="7e879-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="7e879-128">小規模のプログラムを完全に実行またはデバッグする場合に便利です (数十の量子ビット未満)。</span><span class="sxs-lookup"><span data-stu-id="7e879-128">Useful for fully executing or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="7e879-129">[リソース エスティメーター](xref:microsoft.quantum.machines.resources-estimator):量子コンピューターで Q# 演算の特定のインスタンスを実行するために必要なリソースを推定します。</span><span class="sxs-lookup"><span data-stu-id="7e879-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="7e879-130">[トレース シミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro):量子コンピューターの状態を実際にシミュレートせずに、量子プログラムを実行します。そのため、数千もの量子ビットを使用する量子プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7e879-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="7e879-131">量子プログラム内のクラシック コードをデバッグする場合や、必要なリソースを推定する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="7e879-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="7e879-132">[Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator):特別な用途のための量子シミュレーターで、数百万の量子ビットで使用できますが、限定された量子演算のセット (X、CNOT、およびマルチ制御 X) を使用するプログラムに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7e879-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="7e879-133">クイック リファレンス ページ</span><span class="sxs-lookup"><span data-stu-id="7e879-133">Quick Reference Pages</span></span>

- <span data-ttu-id="7e879-134">[IQ# マジック コマンド](xref:microsoft.quantum.guide.quickref.iqsharp):Q# Jupyter Notebook 内の IQ# マジック コマンドのクイック リファレンス ページ。</span><span class="sxs-lookup"><span data-stu-id="7e879-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
