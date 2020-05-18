---
title: Q# ユーザー ガイド
description: ユーザー ガイドの目的と内容の概要
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430613"
---
# <a name="the-q-user-guide"></a><span data-ttu-id="ca528-103">Q# ユーザー ガイド</span><span class="sxs-lookup"><span data-stu-id="ca528-103">The Q# User Guide</span></span>

<span data-ttu-id="ca528-104">Q# ユーザー ガイドへようこそ。</span><span class="sxs-lookup"><span data-stu-id="ca528-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="ca528-105">ここでは、Q# 言語の主要概念と、量子プログラムを記述するために必要なすべての情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca528-105">Here we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="ca528-106">ユーザー ガイドの内容</span><span class="sxs-lookup"><span data-stu-id="ca528-106">User Guide Contents</span></span>

- <span data-ttu-id="ca528-107">[Q# の基本](xref:microsoft.quantum.guide.basics): Q# プログラミング言語の目的と機能に関する概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca528-107">[Q# Basics](xref:microsoft.quantum.guide.basics): an introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

### <a name="q-language"></a><span data-ttu-id="ca528-108">Q# 言語</span><span class="sxs-lookup"><span data-stu-id="ca528-108">Q# Language</span></span>

- <span data-ttu-id="ca528-109">[Q# の型](xref:microsoft.quantum.guide.types): Q# 型モデルを紹介し、型を指定して操作するための構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca528-109">[Types in Q#](xref:microsoft.quantum.guide.types): lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="ca528-110">[型式](xref:microsoft.quantum.guide.expressions): Q# の各型の値を指定、参照、結合、および操作する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="ca528-110">[Type Expressions](xref:microsoft.quantum.guide.expressions): details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="ca528-111">Q# の使用</span><span class="sxs-lookup"><span data-stu-id="ca528-111">Using Q#</span></span>

- <span data-ttu-id="ca528-112">[Q# のファイル構造](xref:microsoft.quantum.guide.filestructure): `*.qs` Q# ファイルの構造と構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca528-112">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="ca528-113">[演算と関数](xref:microsoft.quantum.guide.operationsfunctions): Q# 言語の 2 つの呼び出し可能な型について詳しく説明します。すなわち、"*演算*" (量子ビットに対するアクションを含みます) と "*関数*" (従来の情報と厳密に連携して機能します) です。</span><span class="sxs-lookup"><span data-stu-id="ca528-113">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): details the two callable types of the Q# language: *operations*, which include action on qubit registers and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="ca528-114">ここでは、adjoint および制御されたバージョンの量子操作を含め、これらを定義して呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca528-114">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="ca528-115">[変数](xref:microsoft.quantum.guide.variables): Q# プログラム内における変数の役割と、それらを効果的に活用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca528-115">[Variables](xref:microsoft.quantum.guide.variables): describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="ca528-116">たとえば、バインド スコープに関する情報に加えて、変更できない変数と変更可能な変数の違い、およびそれらを割り当て/再割り当てする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="ca528-116">For example, you can find information about binding scopes, as well as the difference between immutable/mutable variables and how to assign/re-assign them.</span></span>

- <span data-ttu-id="ca528-117">[量子ビットの操作](xref:microsoft.quantum.guide.qubits): 個別の量子ビットと量子ビットのシステムに対処するために使用できる Q# の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca528-117">[Working with qubits](xref:microsoft.quantum.guide.qubits): describes the features of Q# used to address individual qubits and systems of qubits.</span></span> 
    <span data-ttu-id="ca528-118">具体的には、それらの割り当て、それらに対する演算の実行、そして最終的にそれらの測定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca528-118">Specifically, that entails their allocation, performing operations on them, and ultimately their measurement.</span></span> 

- <span data-ttu-id="ca528-119">[制御フロー](xref:microsoft.quantum.guide.controlflow): Q# で使用できるプログラミング制御フロー パターンについて詳しく説明します。これには、多くの標準的な手法 (条件付き実行、for ループ、while ループなど) に加え、量子固有の "成功するまで繰り返す" パターンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca528-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): details the programming control flow patterns available in Q#, which includes many standard techniques (conditional execution, for loops, while loops, etc.) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="ca528-120">[テストとデバッグ](xref:microsoft.quantum.guide.testingdebugging): 自分のコードが想定どおりに動作していることを確かめるためのいくつかの手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca528-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="ca528-121">量子情報の一般的な不透明性により、量子プログラムのデバッグには特殊な手法が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ca528-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="ca528-122">さいわい、Q# では、プログラマーが慣れている従来のデバッグ手法の多くと、量子特有の手法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ca528-122">Fortunately, Q# supports many of the classical debugging techniques programmers are used to, as well as those that are quantum-specific.</span></span> <span data-ttu-id="ca528-123">これには、Q# での単体テストの作成や実行、コード内の値と確率に対する "*アサーション*" の埋め込み、ターゲット コンピューターの状態を出力する `Dump` 関数などが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ca528-123">These include creating/running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the state of target machine.</span></span> 
    <span data-ttu-id="ca528-124">その後者を完全状態シミュレーターと共に使用して、いくつかの量子限界を回避することで計算の特定の部分をデバッグすることができます (例: 量子複製不可能定理)。</span><span class="sxs-lookup"><span data-stu-id="ca528-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations (e.g. the no-cloning theorem).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="ca528-125">量子シミュレーターとリソース エスティメーター</span><span class="sxs-lookup"><span data-stu-id="ca528-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="ca528-126">[量子シミュレーターとホスト アプリケーション](xref:microsoft.quantum.machines): 使用可能なさまざまなシミュレーターの概要と、ホスト プログラムとターゲット コンピューター間の一般的な実行モデル。</span><span class="sxs-lookup"><span data-stu-id="ca528-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): an overview of the different simulators available, as well as the general execution model between host program and target machines.</span></span>

- <span data-ttu-id="ca528-127">[完全状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator): 完全な量子状態をシミュレートするターゲット マシン。</span><span class="sxs-lookup"><span data-stu-id="ca528-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): the target machine which simulates the full quantum state.</span></span> <span data-ttu-id="ca528-128">小規模のプログラムを完全に実行またはデバッグする場合に便利です (24 量子ビット未満)。</span><span class="sxs-lookup"><span data-stu-id="ca528-128">Useful for fully executing or debugging smaller scale programs (less than a couple dozen qubits)</span></span>

- <span data-ttu-id="ca528-129">[リソース エスティメーター](xref:microsoft.quantum.machines.resources-estimator): 量子コンピューターで Q# 演算の特定のインスタンスを実行するために必要なリソースを推定します。</span><span class="sxs-lookup"><span data-stu-id="ca528-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="ca528-130">[トレース シミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro): 量子コンピューターの状態を実際にシミュレートせずに、量子プログラムを実行します。そのため、数千もの量子ビットを使用する量子プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ca528-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="ca528-131">量子プログラム内のクラシック コードをデバッグする場合や、必要なリソースを推定する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ca528-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="ca528-132">[Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator): 特別な用途のための量子シミュレーターで、数百万の量子ビットで使用できますが、限定された量子操作のセット (X、CNOT、およびマルチ制御 X) を使用するプログラムに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca528-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): a special purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations (namely X, CNOT, and multi-controlled X).</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="ca528-133">クイック リファレンス ページ</span><span class="sxs-lookup"><span data-stu-id="ca528-133">Quick Reference Pages</span></span>

- <span data-ttu-id="ca528-134">[IQ# マジック コマンド](xref:microsoft.quantum.guide.quickref.iqsharp):Q# Jupyter Notebook 内の IQ# マジック コマンドのクイック リファレンス ページ。</span><span class="sxs-lookup"><span data-stu-id="ca528-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
