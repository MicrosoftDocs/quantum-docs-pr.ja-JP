---
title: Q# ユーザー ガイド
description: ユーザー ガイドの目的と内容の概要
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231759"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="8e2ae-103">Q# ユーザー ガイド</span><span class="sxs-lookup"><span data-stu-id="8e2ae-103">The Q# User Guide</span></span>

<span data-ttu-id="8e2ae-104">Q# ユーザー ガイドへようこそ。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="8e2ae-105">このガイドのさまざまなトピックでは、Q#を使用して、量子プログラムを開発するための基本事項をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-105">In the different topics of this guide, we introduce some of the basics for developing quantum programs using Q#.</span></span>

<span data-ttu-id="8e2ae-106">Q# 量子プログラミング言語の完全な仕様とドキュメントについては、[Q# 言語ガイド](xref:microsoft.quantum.qsharp.index)を参照します。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-106">We refer to the [Q# language guide](xref:microsoft.quantum.qsharp.index) for a full specification and documentation of the Q# quantum programming language.</span></span> 

## <a name="user-guide-contents"></a><span data-ttu-id="8e2ae-107">ユーザー ガイドの内容</span><span class="sxs-lookup"><span data-stu-id="8e2ae-107">User Guide Contents</span></span>

- <span data-ttu-id="8e2ae-108">[Q# プログラム](xref:microsoft.quantum.guide.programs):Q# での量子プログラムの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-108">[Q# programs](xref:microsoft.quantum.guide.programs): An quick introduction to quantum programs in Q#.</span></span> 

- <span data-ttu-id="8e2ae-109">[Q# プログラム実行する方法](xref:microsoft.quantum.guide.host-programs): Q# プログラムの実行方法について説明します。また、コマンド ライン、Q# Jupyter Notebook、または Python や .NET 言語で記述された従来のホスト プログラムから、プログラムを呼び出すためのさまざまな方法の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-109">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

- <span data-ttu-id="8e2ae-110">[テストとデバッグ](xref:microsoft.quantum.guide.testingdebugging):自分のコードが想定どおりに動作していることを確かめるためのいくつかの手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-110">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="8e2ae-111">量子情報の一般的な不透明性により、量子プログラムのデバッグには特殊な手法が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-111">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="8e2ae-112">さいわい、Q# では、プログラマーが慣れている従来のデバッグ手法の多くと、量子特有の手法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-112">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="8e2ae-113">これには、Q# での単体テストの作成や実行、コード内の値と確率に対する "*アサーション*" の埋め込み、ターゲット コンピューターの状態を出力する `Dump` 関数などが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-113">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="8e2ae-114">その後者を完全状態シミュレーターと共に使用して、いくつかの量子限界を回避することで計算の特定の部分をデバッグすることができます (例: [量子複製不可能定理](xref:microsoft.quantum.concepts.pauli))。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-114">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="8e2ae-115">量子シミュレーターとリソース エスティメーター</span><span class="sxs-lookup"><span data-stu-id="8e2ae-115">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="8e2ae-116">[量子シミュレーターとホスト アプリケーション](xref:microsoft.quantum.machines):使用可能なさまざまなシミュレーターの概要と、ホスト プログラムとターゲット マシンを連携させて Q# プログラムを実行する方法。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-116">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="8e2ae-117">[完全状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator):完全な量子状態をシミュレートするターゲット コンピューター。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-117">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="8e2ae-118">小規模のプログラムを完全に実行またはデバッグする場合に便利です (数十の量子ビット未満)。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-118">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="8e2ae-119">[リソース エスティメーター](xref:microsoft.quantum.machines.resources-estimator):量子コンピューターで Q# 演算の特定のインスタンスを実行するために必要なリソースを推定します。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-119">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="8e2ae-120">[トレース シミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro):量子コンピューターの状態を実際にシミュレートせずに、量子プログラムを実行します。そのため、数千もの量子ビットを使用する量子プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-120">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="8e2ae-121">量子プログラム内のクラシック コードをデバッグする場合や、必要なリソースを推定する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-121">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="8e2ae-122">[Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator):特別な用途のための量子シミュレーターで、数百万の量子ビットで使用できますが、限定された量子演算のセット (X、CNOT、およびマルチ制御 X) を使用するプログラムに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-122">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="8e2ae-123">クイック リファレンス ページ</span><span class="sxs-lookup"><span data-stu-id="8e2ae-123">Quick Reference Pages</span></span>

- <span data-ttu-id="8e2ae-124">[IQ# マジック コマンド](xref:microsoft.quantum.guide.quickref.iqsharp):Q# Jupyter Notebook 内の IQ# マジック コマンドのクイック リファレンス ページ。</span><span class="sxs-lookup"><span data-stu-id="8e2ae-124">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
