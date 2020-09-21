---
title: I Q# マジックコマンド
description: Q#Jupyter notebook を使用した I マジックコマンドのクイックリファレンスページ Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 75a1e1820e5ca16268c9b11322eb5653094b1a3c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833563"
---
# <a name="ino-locq-magic-commands"></a><span data-ttu-id="8ec44-103">I Q# マジックコマンド</span><span class="sxs-lookup"><span data-stu-id="8ec44-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="8ec44-104">全般</span><span class="sxs-lookup"><span data-stu-id="8ec44-104">General</span></span>

- <span data-ttu-id="8ec44-105">[`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): 構成オプションを設定または照会できます。</span><span class="sxs-lookup"><span data-stu-id="8ec44-105">[`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Allows setting or querying configuration options.</span></span>
- <span data-ttu-id="8ec44-106">[`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): ResourcesEstimator ターゲットコンピューターで指定された関数または操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-106">[`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Runs a given function or operation on the ResourcesEstimator target machine.</span></span>
- <span data-ttu-id="8ec44-107">[`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): 現在使用可能なすべてのマジックコマンドの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-107">[`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="8ec44-108">[`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen): 現在開かれている名前空間とそのエイリアスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-108">[`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen): Lists currently opened namespaces and their aliases.</span></span>
- <span data-ttu-id="8ec44-109">[`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): NuGet パッケージを読み込む機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-109">[`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Provides the ability to load a NuGet package.</span></span>
- <span data-ttu-id="8ec44-110">[`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): このカーネルの現在のパフォーマンスメトリックを報告します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-110">[`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="8ec44-111">[`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project): プロジェクト参照を表示または追加する機能を提供し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="8ec44-111">[`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project): Provides the ability to view or add Q# project references.</span></span> 
- <span data-ttu-id="8ec44-112">[`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): QuantumSimulator ターゲットコンピューターで指定された関数または操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-112">[`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="8ec44-113">[`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): ToffoliSimulator ターゲットコンピューターで指定された関数または操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-113">[`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Runs a given function or operation on the ToffoliSimulator target machine.</span></span>
- <span data-ttu-id="8ec44-114">[`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): 現在の Q# セッションで使用できる操作を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-114">[`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Lists the Q# operations available in the current session.</span></span>
- <span data-ttu-id="8ec44-115">[`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): 現在のワークスペースに関連するアクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-115">[`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Provides actions related to the current workspace.</span></span>

### <a name="azure-quantum-integration"></a><span data-ttu-id="8ec44-116">Azure クォンタムの統合</span><span class="sxs-lookup"><span data-stu-id="8ec44-116">Azure Quantum integration</span></span>

- <span data-ttu-id="8ec44-117">[`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Azure Quantum ワークスペースに接続するか、現在の接続状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-117">[`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Connects to an Azure Quantum workspace or displays current connection status.</span></span>
- <span data-ttu-id="8ec44-118">[`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Azure Quantum ワークスペースでジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-118">[`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Runs a job in an Azure Quantum workspace.</span></span>
- <span data-ttu-id="8ec44-119">[`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): 現在の Azure クォンタムワークスペースのジョブの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-119">[`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Displays a list of jobs in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="8ec44-120">[`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): 現在の Azure クォンタムワークスペースにジョブの結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-120">[`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Displays results for a job in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="8ec44-121">[`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): 現在の Azure クォンタムワークスペースのジョブの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-121">[`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Displays status for a job in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="8ec44-122">[`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Azure Quantum ワークスペースにジョブを送信します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-122">[`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Submits a job to an Azure Quantum workspace.</span></span>
- <span data-ttu-id="8ec44-123">[`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Azure Quantum ワークスペースでのジョブ送信のアクティブな実行ターゲットを設定または表示 Q# します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-123">[`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Sets or displays the active run target for Q# job submission in an Azure Quantum workspace.</span></span>

### <a name="chemistry-from-microsoftquantumchemistry-package"></a><span data-ttu-id="8ec44-124">化学 (Microsoft の Quantum パッケージから)</span><span class="sxs-lookup"><span data-stu-id="8ec44-124">Chemistry (from Microsoft.Quantum.Chemistry package)</span></span>

- <span data-ttu-id="8ec44-125">[`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): 指定された yaml ファイルから Broombridge の電子構造の問題表現を読み込んで返します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-125">[`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="8ec44-126">[`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): の Hamiltonian on が、で利用できる形式にエンコードさ Q# れます。</span><span class="sxs-lookup"><span data-stu-id="8ec44-126">[`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="8ec44-127">[`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Hamiltonian 上の対象に用語を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-127">[`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="8ec44-128">[`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): 電子構造の問題のために、Hamiltonian 上にあるので、このデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="8ec44-128">[`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="8ec44-129">問題はファイルから読み込まれるか、引数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="8ec44-129">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="8ec44-130">[`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Broombridge の電子構造問題を読み込み、選択した入力状態を返します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-130">[`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="katas-from-microsoftquantumkatas-package"></a><span data-ttu-id="8ec44-131">Katas (Katas パッケージから)</span><span class="sxs-lookup"><span data-stu-id="8ec44-131">Katas (from Microsoft.Quantum.Katas package)</span></span>

- <span data-ttu-id="8ec44-132">[`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): 1 つのテストを実行し、テストが成功したかどうかを報告します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-132">[`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Runs a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="8ec44-133">[`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): 1 つの kata のテストの参照の実装を確認します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-133">[`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="8ec44-134">具体的には、1つのタスクの参照実装をセルに置き換え、テストが成功したかどうかを報告します。</span><span class="sxs-lookup"><span data-stu-id="8ec44-134">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
